# Optimized Digital Support Service Using LLM and Retrieval-Augmented Generation (RAG)

## 📌 Project Overview

Traditional IT service desk systems often require technicians to manually analyze support tickets, search knowledge bases, and identify suitable solutions. This process can increase resolution effort and create additional workloads for support teams.

This project explores an AI-powered digital support service that combines **Large Language Models (LLMs)** with **Retrieval-Augmented Generation (RAG)** to generate contextual, domain-specific solutions for IT support tickets.

The system retrieves relevant information from historical tickets and organizational knowledge bases, then uses an LLM to generate suggested solutions. These suggestions help technicians resolve issues more efficiently while retaining human judgment in the support workflow.

The seminar study evaluates the approach in a production IT service desk environment, focusing on solution adoption, technician engagement, and practical effectiveness.

## 🎯 Objectives

- Automate parts of the IT support ticket resolution process.
- Use LLMs to generate context-aware support solutions.
- Apply RAG to retrieve relevant information from historical tickets and knowledge bases.
- Use embeddings for semantic similarity search.
- Reduce manual effort and cognitive load for IT technicians.
- Improve access to organizational knowledge.
- Evaluate AI-generated solutions through real-world technician feedback.

## 🏗️ System Architecture

The proposed system consists of several interconnected modules.

### 1. Ticket Processing
- Retrieve new and open tickets from the service desk through an API.
- Analyze ticket descriptions, metadata, and previous resolution information.
- Normalize ticket content for further processing.

### 2. Knowledge Base Preparation
- Extract knowledge articles from SharePoint.
- Divide documents into manageable text chunks.
- Generate vector embeddings for the chunks.
- Store the processed content in a local vector database.

### 3. Retrieval and Ranking
- Convert the incoming ticket into an embedding.
- Search the knowledge base for semantically similar content.
- Extract relevant keywords from ticket metadata.
- Combine semantic similarity and keyword-based relevance to rank results.
- Select the most relevant information for the LLM.

### 4. LLM-Based Solution Generation
- Construct a prompt containing the ticket information and retrieved context.
- Generate a contextual solution using the LLM.
- Format the response with a solution, disclaimer, and source links.

### 5. Ticket Update
- Return the generated solution to the service desk workflow.
- Update the relevant ticket with the proposed response.
- Allow technicians to review, retain, modify, or remove the suggestion.

## 🔄 Workflow

```text
Incoming IT Support Ticket
          |
          v
   Ticket Processing
          |
          v
  Ticket Normalization
          |
          v
    Ticket Embedding
          |
          v
  Hybrid Information Retrieval
   /                    \
  v                      v
Vector Similarity     Keyword Search
  \                      /
   \                    /
          v
  Relevant Context Selection
          |
          v
    Prompt Construction
          |
          v
    LLM Response Generation
          |
          v
  Solution Formatting
          |
          v
   Service Desk Ticket Update
          |
          v
 Technician Review and Feedback
```

## 🛠️ Technologies and Tools

The seminar materials describe the following technologies and tools:

- **Large Language Models (LLMs)** – Generate contextual support solutions.
- **Retrieval-Augmented Generation (RAG)** – Combine retrieved knowledge with language generation.
- **Text Embeddings** – Represent tickets and knowledge articles as vectors.
- **Vector Database** – Store embeddings and support semantic retrieval.
- **Python** – Automation and data processing.
- **Selenium** – Scrape knowledge articles from SharePoint.
- **REST APIs** – Retrieve and update service desk tickets.
- **Azure OpenAI Service** – Referenced in the seminar materials.
- **OpenAI GPT-3.5-Turbo** – Referenced as the language model.
- **OpenAI text-embedding-ada-002** – Referenced for embedding generation.
- **Microsoft Graph** – Referenced for Microsoft ecosystem integration.

The exact software versions, deployment configuration, and dependencies should be documented when the implementation is available.

## 🧠 Key Features

### Semantic Search
Uses embeddings to identify relevant knowledge articles and previous ticket resolutions based on meaning rather than exact keyword matches alone.

### Hybrid Retrieval
Combines semantic similarity with ticket keywords and metadata to improve the relevance of retrieved information.

### Smart Chunking
Splits lengthy knowledge articles into smaller text segments suitable for embedding and retrieval.

### Context-Aware Generation
Supplies the retrieved information to the LLM so that its response is grounded in relevant support knowledge.

### Automated Ticket Processing
The presented workflow describes fetching up to 100 new or open tickets through an API.

### Knowledge Base Automation
Uses a Selenium-based scraper to extract SharePoint articles and store them locally for retrieval.

### Technician Feedback
Allows technicians to assess AI-generated solutions, providing information about their practical usefulness and adoption.

## 📊 Experimental Setup and Results

The seminar study reports a two-week evaluation in a production IT support environment.

| Metric | Reported Result |
|---|---:|
| Evaluation duration | 2 weeks |
| Tickets analyzed | 401 out of 532 |
| AI-generated solutions adopted | 38.4% |
| Solutions removed | 60.6% |
| Solutions modified | 1% |
| Hardware ticket success | 100% |
| VPN ticket success | 75% |
| IT equipment disposal retention | 61.7% |

The report also indicates that technicians rated the system as useful for simple tickets, with a score of 4/5, while active adoption for complex tasks was lower, at 2.33/5.

**Interpretation:** The findings suggest that AI-generated solutions can assist technicians, particularly with simpler and more standardized support requests. However, the relatively low adoption rate indicates that generated responses still require appropriate contextual relevance, validation, and human review.

These figures reflect the seminar study and are not independent benchmarks for all RAG-based support systems.

## 🌟 Advantages

- Reduces the need to search manually through large knowledge bases.
- Provides relevant historical information during ticket resolution.
- Automates repetitive parts of the support workflow.
- Helps technicians get started on common issues more quickly.
- Supports organizational knowledge reuse and continuity.
- Combines semantic retrieval with keyword-based matching.
- Keeps technicians involved in reviewing AI-generated recommendations.

## ⚠️ Challenges and Limitations

- **System integration:** Connecting LLM workflows to existing service desk platforms can be challenging.
- **Unstructured data:** Ticket descriptions and knowledge articles require preprocessing and normalization.
- **Language limitations:** English-centric models may provide less relevant results for Swedish-language tickets.
- **Variable adoption:** Technicians may remove or modify generated solutions if they are not sufficiently useful.
- **Evaluation limitations:** The study identifies a lack of metrics such as BLEU, ROUGE, and METEOR for objective response evaluation.
- **Limited sample:** The two-week evaluation and excluded teams limit the generalizability of the findings.
- **Unmeasured efficiency:** The study does not establish the actual reduction in ticket resolution time.

## 🔮 Future Scope

Potential improvements include:

- Measuring ticket resolution time before and after introducing RAG.
- Evaluating response quality using suitable automated and human-assessment metrics.
- Extending the evaluation to larger datasets and additional support teams.
- Improving multilingual retrieval and response generation.
- Automating ticket classification, routing, and follow-up suggestions.
- Improving retrieval relevance through better embeddings and ranking methods.
- Incorporating technician feedback to improve generated responses.
- Measuring productivity gains, operational costs, and return on investment.
- Investigating advanced adaptation approaches, including reinforcement learning from human feedback (RLHF).

## 🔐 Security and Privacy Considerations

- Protect confidential ticket information and internal knowledge articles.
- Use appropriate authentication and access controls for service desk and knowledge base APIs.
- Avoid exposing sensitive organizational information to unauthorized external services.
- Validate generated solutions before applying changes to production systems.
- Maintain logs and review mechanisms for automated ticket updates.
- Follow organizational data retention and privacy requirements.

## 🚀 Implementation Status

This README documents the system described in the seminar materials.

The availability of executable source code, configuration files, API credentials, a deployed service, and reproducible evaluation scripts depends on what is included in the repository. The seminar description alone does not establish that a complete implementation is publicly available.

## 🎓 Academic Information

**Seminar Title:** Optimized Digital Support Service Using LLM and Retrieval-Augmented Generation

**Student:** Lipakshi Panda

**Branch:** Computer Science and Engineering (AI/ML)

**Institution:** Odisha University of Technology and Research, Bhubaneswar, Odisha

**Under the Guidance of:** Dr. Simanta Kumar Nayak

## 📚 Reference

Cederlund, Oscar, Sadi Alawadi, and Feras M. Awaysheh. “LLMRAG: An Optimized Digital Support Service using LLM and Retrieval-Augmented Generation.” *Proceedings of the 2024 9th International Conference on Fog and Mobile Edge Computing (FMEC)*, 2024.

DOI: https://doi.org/10.1109/FMEC62297.2024.10710181

---

*This project is based on a seminar study of LLM- and RAG-assisted IT service desk automation.*
