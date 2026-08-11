---
title: "Week 6 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---
### Week 6 Objectives:

* Complete and test end-to-end RAG chatbot.
* Learn logging, monitoring, alerting, and conversation history storage using AWS services.

### Tasks to be carried out this week:

| Day | Task                                                                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                                                                |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | --------------------------------------------------------------------------------- |
| 2   | - Complete legal Q&A chatbot with end-to-end RAG flow.<br />- Test Q&A functionality after data has been loaded into vector store.<br />- Debug retrieval and embedding dimension errors.                                                              | 27/07/2026 | 27/07/2026      |                                                                                   |
| 3   | - Debug database connection and RDS query errors.<br />- Optimize answer quality by adjusting top_k, prompt template, and chunk size.<br />- Re-check retrieval and LLM timeouts.                                                                      | 28/07/2026 | 28/07/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 4   | - Learn Amazon CloudWatch to monitor logs and application performance.<br />- Learn Amazon SNS to send alerts when system errors occur.<br />- Design CloudWatch Alarm and SNS notification flow.                                                      | 29/07/2026 | 29/07/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 5   | - Learn Amazon DynamoDB to store conversation history.<br />- Design table to store chat history by conversation, message, user index, admin date index, and TTL.<br />- Write documentation for the plan to improve speed and apply AWS architecture. | 30/07/2026 | 30/07/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 6   | - Continue testing and fixing UI/chatbot errors.<br />- Write blog post 2.<br />- Write event report.<br />- Continue updating workshop section.<br />- Write Week 6 worklog.                                                                          | 31/07/2026 | 31/07/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |

### Week 6 Achievements:

* RAG Chatbot operates more stably after debugging and testing process.
* Completed design for storing conversation history using DynamoDB.
* Established monitoring/alerting direction using CloudWatch and SNS.
* Completed blog post 2, event report, and Week 6 worklog.
* Coordinated with team to test chatbot end-to-end and recorded arising errors.
* Discussed test results, latency, and answer quality to agree on points needed for optimization.
