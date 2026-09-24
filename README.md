from pydantic import BaseModel, Field
from langchain_core.messages import HumanMessage, SystemMessage
from langchain_groq import ChatGroq


class RAGResult(BaseModel):
    answer: str = Field(
        description="The final answer based on the retrieved documents."
    )

    sources: list[str] = Field(
        description="List of document sources used to answer the query."
    )

    summary: str = Field(
        description="A concise summary of the retrieved information."
    )


class RAGAgent:

    def __init__(self, model_name: str):
        self.llm = ChatGroq(
            model=model_name,
            temperature=0
        )

        self.rag = self.llm.with_structured_output(
            RAGResult
        )

    def answer(self, query: str) -> RAGResult:
        if not query.strip():
            raise ValueError("Query cannot be empty.")

        system_prompt = """You are the RAG Agent of NEXUS.

Answer the user's question using information retrieved from
the knowledge base.

Do not invent information.
If the provided context does not contain enough information,
clearly state that.

Return a clear answer, a concise summary, and the relevant sources.
"""

        messages = [
            SystemMessage(content=system_prompt),
            HumanMessage(content=query)
        ]

        result = self.rag.invoke(messages)

        return result
