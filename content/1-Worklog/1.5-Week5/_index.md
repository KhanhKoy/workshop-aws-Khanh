---
title: "Week 5 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---
### Week 5 Objectives:

* Migrate vector store to Amazon RDS PostgreSQL pgvector.
* Optimize vector search queries and start measuring system performance.

| Day | Task                                                                                                                                                                                                                                                            | Start Date | Completion Date | Reference Material                                                                |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | --------------------------------------------------------------------------------- |
| 2   | - Redirect vector store from local to Amazon RDS PostgreSQL pgvector.<br />- Configure environment variables for RDS connection.<br />- Test PostgreSQL connection from the application.                                                                        | 20/07/2026 | 20/07/2026      |                                                                                   |
| 3   | - Update VectorStore to support FAISS/SQLite when running locally and PostgreSQL pgvector when deploying to cloud.<br />- Create legal_chunks table and vector embedding column in PostgreSQL.<br />- Test chunk and embedding insertion process into database. | 21/07/2026 | 21/07/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 4   | - Learn and implement cosine similarity search using pgvector.<br />- Optimize RDS queries.<br />- Add timeout for PostgreSQL queries.                                                                                                                          | 22/07/2026 | 22/07/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 5   | - Learn and experiment with HNSW/IVFFlat index for pgvector.<br />- Write create_hnsw_index.py and create_ivfflat_index.py scripts.<br />- Add benchmarking and latency measurement for retrieval, embedding, DB search, and LLM.                               | 23/07/2026 | 23/07/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 6   | - Re-test Q&A pipeline after connecting RDS pgvector.<br />- Update README describing RDS/pgvector architecture and how to run project.<br />- Write blog post 1.<br />- Continue updating workshop section.<br />- Write Week 5 worklog.                       | 24/07/2026 | 24/07/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |

### Week 5 Achievements:

* Application supports storing and searching vectors using PostgreSQL pgvector.
* RDS configuration integrated into system via environment variables.
* Created scripts for generating HNSW/IVFFlat indexes for pgvector.
* Completed blog post 1 and updated Week 5 worklog.
