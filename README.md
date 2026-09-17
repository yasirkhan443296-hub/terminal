# terminal


New-Item app\tools\web\search_tool.py, app\tools\rag\retrieval_tool.py, app\tools\database\sql_tool.py, app\tools\utility\calculator_tool.py, app\tools\utility\document_tool.py -ItemType File

New-Item app\ingestion\loaders.py, app\ingestion\cleaner.py, app\ingestion\chunker.py, app\ingestion\metadata.py, app\ingestion\pipeline.py -ItemType File

New-Item app\retrieval\vector_search.py, app\retrieval\keyword_search.py, app\retrieval\hybrid_search.py, app\retrieval\reranker.py, app\retrieval\retriever.py -ItemType File

New-Item app\embeddings\embedding_model.py -ItemType File

New-Item app\generation\llm.py, app\generation\prompts.py, app\generation\response_generator.py -ItemType File

New-Item app\guardrails\input_guardrails.py, app\guardrails\output_guardrails.py, app\guardrails\pii_detection.py, app\guardrails\citation_checker.py -ItemType File

New-Item app\evaluation\ragas_eval.py, app\evaluation\deepeval_eval.py, app\evaluation\metrics.py, app\evaluation\test_dataset.json -ItemType File

New-Item app\memory\conversation_memory.py -ItemType File

New-Item app\database\connection.py, app\database\models.py, app\database\repository.py -ItemType File

New-Item app\config\settings.py, app\config\logging.py -ItemType File

New-Item app\utils\helpers.py, app\utils\exceptions.py, app\utils\constants.py -ItemType File

New-Item frontend\app.py -ItemType File
New-Item frontend\components\chat.py, frontend\components\sources.py, frontend\components\sidebar.py -ItemType File
New-Item frontend\pages\chat_page.py, frontend\pages\documents_page.py, frontend\pages\evaluation_page.py -ItemType File

New-Item tests\unit\test_chunking.py, tests\unit\test_retrieval.py, tests\unit\test_reranker.py, tests\unit\test_agents.py, tests\unit\test_guardrails.py -ItemType File
New-Item tests\integration\test_rag_pipeline.py, tests\integration\test_agent_workflow.py -ItemType File

New-Item scripts\ingest_documents.py, scripts\build_index.py, scripts\run_evaluation.py -ItemType File

New-Item docker\Dockerfile -ItemType File

New-Item .env.example, .gitignore, requirements.txt, README.md, pyproject.toml -ItemType File



# LLM & LangChain
langchain
langchain-core
langchain-community
langchain-groq
langgraph

# Configuration & validation
python-dotenv
pydantic
pydantic-settings

# Embeddings & Vector Search
sentence-transformers
faiss-cpu

# Document processing
pypdf
python-docx
beautifulsoup4

# Web Search
tavily-python

# Database
sqlalchemy

# Frontend
streamlit

# Evaluation
ragas
deepeval

# Testing
pytest

# Utilities
requests
numpy
pandas


NEXUS/
│
├── app/
│   │
│   ├── agents/
│   │   ├── router_agent.py
│   │   ├── rag_agent.py
│   │   ├── research_agent.py
│   │   ├── sql_agent.py
│   │   └── workflow.py
│   │
│   ├── tools/
│   │   ├── web/
│   │   │   └── search_tool.py
│   │   │
│   │   ├── rag/
│   │   │   └── retrieval_tool.py
│   │   │
│   │   ├── database/
│   │   │   └── sql_tool.py
│   │   │
│   │   └── utility/
│   │       ├── calculator_tool.py
│   │       └── document_tool.py
│   │
│   ├── ingestion/
│   │   ├── loaders.py
│   │   ├── cleaner.py
│   │   ├── chunker.py
│   │   ├── metadata.py
│   │   └── pipeline.py
│   │
│   ├── retrieval/
│   │   ├── vector_search.py
│   │   ├── keyword_search.py
│   │   ├── hybrid_search.py
│   │   ├── reranker.py
│   │   └── retriever.py
│   │
│   ├── embeddings/
│   │   └── embedding_model.py
│   │
│   ├── generation/
│   │   ├── llm.py
│   │   ├── prompts.py
│   │   └── response_generator.py
│   │
│   ├── guardrails/
│   │   ├── input_guardrails.py
│   │   ├── output_guardrails.py
│   │   ├── pii_detection.py
│   │   └── citation_checker.py
│   │
│   ├── evaluation/
│   │   ├── ragas_eval.py
│   │   ├── deepeval_eval.py
│   │   ├── metrics.py
│   │   └── test_dataset.json
│   │
│   ├── memory/
│   │   └── conversation_memory.py
│   │
│   ├── database/
│   │   ├── connection.py
│   │   ├── models.py
│   │   └── repository.py
│   │
│   ├── config/
│   │   ├── settings.py
│   │   └── logging.py
│   │
│   └── utils/
│       ├── helpers.py
│       ├── exceptions.py
│       └── constants.py
│
├── frontend/
│   ├── app.py
│   ├── components/
│   │   ├── chat.py
│   │   ├── sources.py
│   │   └── sidebar.py
│   └── pages/
│       ├── chat_page.py
│       ├── documents_page.py
│       └── evaluation_page.py
│
├── data/
│   ├── raw/
│   ├── processed/
│   ├── indexes/
│   └── evaluation/
│
├── tests/
│   ├── unit/
│   │   ├── test_chunking.py
│   │   ├── test_retrieval.py
│   │   ├── test_reranker.py
│   │   ├── test_agents.py
│   │   └── test_guardrails.py
│   │
│   └── integration/
│       ├── test_rag_pipeline.py
│       └── test_agent_workflow.py
│
├── scripts/
│   ├── ingest_documents.py
│   ├── build_index.py
│   └── run_evaluation.py
│
├── docker/
│   └── Dockerfile
│
├── .env.example
├── .gitignore
├── requirements.txt
├── README.md
└── pyproject.toml
