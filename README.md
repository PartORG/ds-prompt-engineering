# Prompt Engineering with LangChain

## Introduction

**Prompt engineering** is the practice of designing and refining inputs (prompts) to guide Large Language Models (LLMs) toward producing desired outputs. Well-crafted prompts can dramatically improve the quality, accuracy, and relevance of AI-generated responses.

This workshop teaches you practical prompt engineering techniques using the **LangChain** framework—a popular Python library for building LLM applications—with Groq's free LLM API through hands-on exercises.

## Requirements

- Python 3.11.3
- langchain (latest version)
- langchain-groq (latest version)
- jupyterlab (latest version)
- python-dotenv (latest version)
- langchain-core (latest version)

## Installation

To set up the project, follow these steps:

1. Clone the repository:
   ```sh
   git clone https://github.com/PartORG/ds-prompt-engineering.git
   cd ds-prompt-engineering
   ```

2. Create a virtual environment and activate it:
   ```sh
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. Install the dependencies:
   ```sh
   pip install -r requirements.txt
   ```

4. Set up your environment variables (if needed):
   ```sh
   cp .env.example .env
   nano .env  # Add your Groq API key if required
   ```

## Usage

To run the workshop, follow these steps:

1. Start JupyterLab:
   ```sh
   jupyter lab
   ```

2. Open the notebooks in sequence:
   - **[1_intro_langchain.ipynb](1_intro_langchain.ipynb)**: Introduction to LangChain
   - **[2_langchain_prompt_engineering.ipynb](2_langchain_prompt_engineering.ipynb)**: Prompt Engineering with LangChain

These notebooks will guide you through the fundamentals of LangChain and practical techniques for prompt engineering.