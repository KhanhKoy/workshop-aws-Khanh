---
title: "Week 3 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---
### Week 3 Objectives:

* Build a complete RAG Q&A flow for the legal chatbot.
* Integrate the Chainlit interface and design initial AWS architecture for the application.

### Tasks to be carried out this week:

| Day | Task                                                                                                                                                                                                                                                                                                                                             | Start Date | Completion Date | Reference Material                                                                |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | --------------------------------------------------------------------------------- |
| 2   | - Build a complete RAG Q&A flow for the legal chatbot.<br />- Complete module retriever.py to retrieve relevant chunks.<br />- Test retrieval results with legal data.                                                                                                                                                                           | 06/07/2026 | 06/07/2026      |                                                                                   |
| 3   | - Complete module prompt.py to generate prompts based on questions and context.<br />- Design suitable prompts for the Vietnamese legal chatbot.<br />- Adjust the way source documents are included in responses                                                                                                                                | 07/07/2026 | 07/07/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 4   | - Complete module generator.py to generate responses from LLM.<br />- Add the option to choose between Gemini or Amazon Bedrock providers.<br />- Learn about Amazon Bedrock Runtime for the LLM generation module.                                                                                                                              | 08/07/2026 | 08/07/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 5   | - Complete module qa_service.py to connect retriever, prompt, and generator.<br />- Create a chat interface using Chainlit in app.py.<br />- Integrate Chainlit with RAG core.                                                                                                                                                                   | 09/07/2026 | 09/07/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 6   | - Learn application architecture running on Amazon EC2.<br />- Design an initial AWS architecture diagram with ALB, EC2, RDS pgvector, and Bedrock.<br />- Update workshop content based on completed tasks.<br />- Write Week 3 worklog.<br />- Discuss with the team regarding RAG flow, retrieval results, and chatbot improvement direction. | 10/07/2026 | 10/07/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |

### Week 3 Achievements:

* Completed RAG Q&A flow including retrieval, prompt, and generation.
* Chainlit interface integrated with RAG core.
* Application is capable of receiving questions and answering based on legal data.
* An initial AWS architecture design for the system is available.
* Discussed with team members about the RAG processing flow and task division among data, backend, and interface.
* Reviewed retrieval results and chatbot responses with the team to determine directions for improvement.
