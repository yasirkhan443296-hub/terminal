from pydantic import BaseModel, Field
from langchain_core.messages import HumanMessage, SystemMessage
from langchain_groq import ChatGroq


class ResearchResult(BaseModel):
    answer: str = Field(
        description="The final research answer."
    )

    sources: list[str] = Field(
        description="List of source URLs used for the research."
    )

    summary: str = Field(
        description="A short summary of the research."
    )


class ResearchAgent:

    def __init__(self, model_name: str):
        self.llm = ChatGroq(
            model=model_name,
            temperature=0
        )

        self.researcher = self.llm.with_structured_output(
            ResearchResult
        )

    def research(self, query: str) -> ResearchResult:
        if not query.strip():
            raise ValueError("Query cannot be empty.")

        system_prompt = """You are the research agent of NEXUS.
Analyze research information and produce a clear, factual answer
with a concise summary and sources."""

        messages = [
            SystemMessage(content=system_prompt),
            HumanMessage(content=query)
        ]

        result = self.researcher.invoke(messages)

        return result

