---
title: "Event 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---
# Summary Report: “AWS FCAJ Agent Forge - Deepdive Day 1”

### Event Objectives

* **Provide a comprehensive overview (Introduction)** of the Agentic AI ecosystem and the levels of autonomy in artificial intelligence.
* **Deep dive into the architecture** of the Amazon Bedrock AgentCore L300 infrastructure (advanced level), focusing on 3 core components: Runtime, Gateway, and Identity.
* **Experience the next-generation programming environment (Vibe Coding)** by configuring and setting up a basic AI Agent project.

### Speakers

* **Nghia** - AWS Expert, in charge of presenting the in-depth theory regarding the AgentCore L300 architecture.
* **Hai Anh** - AWS Expert, directly leading the environment configuration and Hands-on Lab.

### Key Highlights (Core Theory)

#### Amazon Bedrock AgentCore L300 Architecture

* **Runtime:** Provides a fully serverless execution environment, utilizing MicroVM technology to safely isolate each user's communication session. The system auto-scales and bills flexibly based on actual usage traffic.
* **Identity:** Acts as a security checkpoint, controlling identities and permissions. AgentCore uses a token conversion mechanism (Workload Access Token - WAT) to encrypt user identities before communicating with external tools, ensuring no sensitive data leakage.
* **Gateway:** The central management middleware layer that standardizes connections from hundreds of Agents to external APIs. The Gateway integrates a Human-in-the-loop process, allowing human administrators to intervene, approve, or reject critical AI decisions.

#### Hands-on Lab Content

The practical session focused on setting up the Vibe Coding environment and deploying an Agent through natural interaction with the Kiro AI assistant. The lab content included the following parts:

* **IDE and Environment Setup:** Installing dependencies (Node.js, Python, AWS CDK, AgentCore CLI) and configuring AWS credentials. Setting up the `steering` document to provide context for the Kiro assistant.
* **Deploy a Basic Agent:** Using the `agent core create` command line for the system to auto-generate the source code. The LLM configuration was adjusted to the `Nova Micro` model to optimize development costs.
* **Launch Local Testing Environment:** After the source code is generated, the next step is to navigate the terminal to the project's root directory (e.g., specifically at `C:\Users\khanh\AgentCoreProject> cd AgentCoreProject`) and launch the local development environment using the `agentcore dev` command.

### Key Takeaways & Applications

#### Paradigm Shift in Software Development

* **The Power of Vibe Coding:** Although only taking the initial setup steps, observing the AI IDE automatically read the context and generate the Agent source code proved a clear shift from "manual coding" to "describing solutions."
* **Cloud Cost Optimization:** The skill of customizing LLM configuration files to switch to compact, low-cost models during the local testing phase is a highly practical reflex to avoid unexpected costs when working on a personal account.

#### The Reality of Cloud Infrastructure Deployment (IaC)

- The agonizing wait when running the `agentcore dev` command is a practical testament that automating cloud infrastructure deployment never happens instantly. This experience brings a hard-learned lesson about the necessity of carefully estimating deployment time when designing and operating complex RAG systems or Legal Assistant Chatbots in the future, preventing service disruptions for end users.

### Applications in Work & Study

* **Upgrading Security for RAG Architecture:** The Identity concept and Workload Access Token (WAT) mechanism from AgentCore provide an excellent template to apply to securing the Legal Assistant Chatbot system. By setting up a similar Gateway layer, workflows retrieving legal documents from the RDS PostgreSQL (pgvector) database or API calls to Amazon Bedrock will be strictly identity-controlled, ensuring privacy and safe access authorization.
* **Optimizing the Development Process with Vibe Coding:** Leveraging AI-integrated IDEs (like Kiro) completely changes the approach to building APIs with FastAPI or configuring LangChain. Instead of wasting time writing basic boilerplate code, natural language can be used for the AI to auto-generate code, thereby dedicating all the time to solving tougher problems regarding asynchronous processing flows (such as optimizing performance with `asyncio.to_thread`) or fine-tuning knowledge compression strategies.
* **More Efficient Cloud Infrastructure Management (IaC):** The experience of waiting for the configuration from the `agentcore dev` command is a practical lesson in resource management. When building an Ingestion pipeline to store documents on S3, SQS, or DynamoDB, applying infrastructure automation (CloudFormation/CDK) needs to be systematically planned. There must be a clear separation between the development (dev) and production environments to prevent cloud resource provisioning time from disrupting the software testing process.

### Event Experiences and Reflections

* **The Harsh Reality of Cloud Deployment:** The most memorable highlight of the session wasn't necessarily the smooth theories, but the moment the entire auditorium "stared at the screen" waiting for the system to run the `agentcore dev` command. This experience reflects a very typical truth of the software engineering profession: cloud infrastructure automation is highly powerful, but actual resource provisioning takes considerable time and always requires patience.
* **The Shift from "Manual Coder" to "Solution Architect":** Witnessing the AI read and understand the `steering` document to auto-setup the entire project skeleton provided a fresh perspective. Modern developers are gradually stepping away from meticulously typing every line of syntax, moving toward the role of a director—where the skills of describing problems, designing systems, and directing business logic flows become more crucial than ever.
* **The Foundational Stepping Stone is the Biggest Challenge:** The fact that the entire practical time was consumed by environment preparation (installing CLI, CDK, configuring Access Keys) shows that the biggest barrier when approaching new Cloud technologies usually doesn't lie in the code, but in setting up the ecosystem. This reflection helps me better prepare my mindset and troubleshooting skills for upcoming complex projects at the university as well as in major tech arenas.

#### Some event photos

![1786296927712](image/_index/1786296927712.jpg)
