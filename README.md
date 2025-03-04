Deep Research AI Agentic System
Overview
This project is an AI-driven research system that gathers online information using Tavily and processes it with a dual-agent system using LangChain and LangGraph. It employs Mistral-7B (via Ollama) as a free LLM for answer generation.

Components
Research Agent: Crawls the web using Tavily API.
Answer Agent: Processes collected data and generates structured answers.
LangGraph & LangChain: Manages multi-agent workflows.
Installation
Ensure you have Python installed, then run:

bash
Copy
Edit
pip install langchain langgraph tavily-python ollama
ollama pull mistral
Usage
Run the following Python script to test the system:

python
Copy
Edit
import os
from langchain.chat_models import ChatOllama
from langchain.tools import TavilySearchResults

os.environ["TAVILY_API_KEY"] = "your_api_key_here"

llm = ChatOllama(model="mistral")
search = TavilySearchResults(max_results=3)

def research_and_answer(query):
    results = search.invoke(query)
    response = llm.invoke(f"Summarize: {results}")
    return response.content

print(research_and_answer("Latest AI trends"))
How It Works
User Input: The user enters a research query.
Research Agent: Uses Tavily API to collect relevant data from the web.
Answer Agent: Mistral-7B processes the data and generates an informative response.
Output: A structured answer is displayed to the user.
Project Submission
GitHub Repo: Upload your project code and README.
Documentation: Provide an explanation of your implementation.
Send Details to: contact@kairon.co.in by 7th March 2025.
Selection Process: Code review → Interview.
🚀 Build a robust, intelligent research agent system!
