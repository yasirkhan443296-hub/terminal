# terminal

mkdir NEXUS
cd NEXUS

mkdir app, frontend, data, tests, scripts, docker
mkdir app\agents, app\tools, app\ingestion, app\retrieval, app\embeddings, app\generation, app\guardrails, app\evaluation, app\memory, app\database, app\config, app\utils
mkdir app\tools\web, app\tools\rag, app\tools\database, app\tools\utility
mkdir frontend\components, frontend\pages
mkdir data\raw, data\processed, data\indexes, data\evaluation
mkdir tests\unit, tests\integration

New-Item app\agents\router_agent.py, app\agents\rag_agent.py, app\agents\research_agent.py, app\agents\sql_agent.py, app\agents\workflow.py -ItemType File

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
