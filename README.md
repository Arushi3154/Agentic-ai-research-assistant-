# Agentic-ai-research-assistant-
Agentic Literature Reviewer
This project leverages LangGraph, Claude API, and arXiv API to create an autonomous research assistant. It automates the end-to-end process of literature discovery, content synthesis, and report generation.
Overview
The Agentic Literature Reviewer is designed to transform a broad research topic into a structured, academic-style literature review. It performs iterative searches, filters relevant papers, vectorizes content using Chroma, and utilizes Claude's reasoning capabilities to compare methodologies and synthesize findings.
 Tech Stack
Orchestration: LangGraph (for stateful, multi-step agent workflows)
LLM: Anthropic Claude API
Search: arXiv API
Vector Database: Chroma (for RAG-based document retrieval)
⚙️ How It Works
The agent operates as a graph-based state machine with the following nodes:
Searcher: Queries arXiv for the most recent and relevant papers based on the user topic.
Summarizer: Downloads abstracts (and full text where available), creating structured summaries.
Embedder: Stores paper data in a Chroma vector database for efficient semantic retrieval.
Comparator: Retrieves papers from the database to perform cross-paper method analysis.
Writer: Synthesizes the aggregated data into a structured Markdown literature review.
 Getting Started
Prerequisites
Python 3.10+
An Anthropic API Key
Installation
Bash
# Clone the repository
git clone https://github.com/Arushi3154/agentic-lit-reviewer
cd agentic-lit-reviewer

# Install dependencies
pip install -r requirements.txt
Configuration
Create a .env file in the root directory and add your credentials:
Code snippet
ANTHROPIC_API_KEY=your_claude_api_key_here
 Usage
To initiate a literature review, run the main entry point:
Bash
python main.py --topic "Attention mechanisms in Transformers" --limit 5
The agent will output a literature_review.md file in the ./reports directory, containing:
Executive Summary
Methodology Comparison Table
Key Findings
References
🔑 Key Features
Autonomous Iteration: If the initial search yields poor results, the agent is configured to refine its query automatically.
Methodological Comparison: Rather than just summarizing, the agent uses RAG to extract specific technical comparisons across papers.
Extensible Design: Easily swap arXiv for other research databases (e.g., Semantic Scholar or PubMed) by modifying the Searcher node.
📝 Roadmap
[ ] Add support for local PDF ingestion.
[ ] Integrate graph visualization to show paper relationships.
[ ] Export reports to LaTeX/PDF format.
This project is intended for research purposes. Ensure you comply with the terms of service of all connected APIs.
