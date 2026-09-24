from typing import Literal

from pydantic import BaseModel, Field
from langchain_core.messages import HumanMessage, SystemMessage
from langchain_groq import ChatGroq


class RouterDecision(BaseModel):
    destination: Literal[
        "rag_agent",
        "research_agent",
        "sql_agent",
    ] = Field(
        description="The agent that should handle the user's query."
    )

    reasoning: str = Field(
        description="Short explanation for the routing decision."
    )


class RouterAgent:
    """Routes user queries to the appropriate specialized agent."""

    def __init__(self, model_name: str):
        self.llm = ChatGroq(
            model=model_name,
            temperature=0,
        )

        self.router = self.llm.with_structured_output(
            RouterDecision
        )

    def route(self, query: str) -> RouterDecision:
        if not query.strip():
            raise ValueError("Query cannot be empty.")

        system_prompt = """
You are the Router Agent of NEXUS.

Choose the correct specialized agent.

rag_agent:
Questions about uploaded documents and knowledge base.

research_agent:
Web research, current information, news, and external information.

sql_agent:
Database questions, structured data, and SQL queries.

Choose exactly one agent.
Do not answer the user's question.
Only return the routing decision.
"""

        messages = [
            SystemMessage(content=system_prompt),
            HumanMessage(content=query),
        ]

        return self.router.invoke(messages)
