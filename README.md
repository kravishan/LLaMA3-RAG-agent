# LLaMA3-RAG-agent

LLaMA3-RAG-agent is a repository showcasing an implementation of a retrieval-augmented generation (RAG) agent using LLaMA3 (Large Language Model for Mediation Agent 3). This project integrates advanced natural language processing techniques for document retrieval, analysis, and question-answering tasks. It includes functionalities for indexing documents from specified URLs, enhancing user queries using a search query generator, and grading answers based on relevance and factual accuracy. Explore how LLaMA3-RAG-agent can facilitate complex information retrieval and generation tasks in various domains.

![diagram](https://github.com/kravishan/LLaMA3-RAG-agent/assets/125926016/d30c27ff-6f56-47f9-bf46-28676c5bfab7)


This repository implements an agent that combines ideas from different retrieval-augmented generation (RAG) papers:

- **Routing:** This agent incorporates the adaptive retrieval-augmented generation (RAG) approach ([paper](https://arxiv.org/abs/2403.14403)), which routes questions to different retrieval methods based on adaptive strategies.
- **Fallback:** Inspired by the Corrective RAG approach ([paper](https://arxiv.org/pdf/2401.15884.pdf)), the agent includes a fallback mechanism to perform web searches when retrieved documents are not relevant to the query.
- **Self-correction:** The agent leverages concepts from Self-RAG ([paper](https://arxiv.org/abs/2310.11511)) to improve answers by correcting hallucinations or addressing questions more effectively.


## Introduction

LLaMA3-RAG-agent is a project that demonstrates how to leverage LLaMA3, a large language model, for retrieval-augmented generation tasks. It integrates document indexing, retrieval, and grading functionalities using LangChain and other associated tools.

## Setup

To set up the project locally, follow these steps:

1. Clone the repository:

   ```bash
   git clone https://github.com/kravishan/LLaMA3-RAG-agent.git
   cd LLaMA3-RAG-agent

2. Install dependencies:

    ```bash
    pip install -U langchain-nomic langchain_community tiktoken langchainhub langchain-openai chromadb langchain langgraph tavily-python nomic[local] langchain-text-splitters

3. Set up environment variables:

     ```bash
    export LANGCHAIN_TRACING_V2=true
    export LANGCHAIN_ENDPOINT=https://api.smith.langchain.com
    export LANGCHAIN_API_KEY=YOUR API KEY

## Indexing Documents

The repository includes functionality to index documents for retrieval. I have added my own websites URLs to retrieve documents. You can add your own URLs using the provided scripts or notebooks.

Example code snippet:

    urls = [
    "https://www.oulu.fi/en/apply/international-programmes",
    "https://www.oulu.fi/en/apply/how-apply/applying-bachelors-programmes",
    "https://www.oulu.fi/en/apply/how-apply/applying-masters-programmes",
    ]

## Retrieval and Grading

Demonstrate how to retrieve documents based on user queries and grade their relevance or correctness.

## Examples

1. **Without Search Query Generator**

   **User Question:** How many master's programs are taught in English?

   In this mode, the system performs a general search based on the user question without additional context or refinements.

2. **With Search Query Generator**

   **User Question:** How many master's programs are taught in English?

   The search query generator analyzes both the user question and the available documents. It enhances the question to be more specific and informative, for example, refining it to: "How many master's programs are taught in English at University of Oulu?" This ensures the search targets exact data requested by the user.




