# ds-prompt-engineering

**Prompt Engineering with LangChain**

[![GitHub Actions](https://github.com/PartORG/ds-prompt-engineering/actions/workflows/workflow-02.yml/badge.svg?branch=main&event=workflow_dispatch)](https://github.com/PartORG/ds-prompt-engineering/actions/workflows/workflow-02.yml)
[![License](https://img.shields.io/github/license/PartORG/ds-prompt-engineering)](LICENSE)

## Introduction

**Prompt engineering** is the practice of designing and refining inputs (prompts) to guide Large Language Models (LLMs) toward producing desired outputs. Well-crafted prompts can dramatically improve the quality, accuracy, and relevance of AI-generated responses.

**Why is prompt engineering important?**
- **Control and precision**: Direct the model to produce specific formats, tones, or types of responses
- **Better results with less effort**: Get accurate answers without fine-tuning or training custom models
- **Cost-effective**: Optimize model performance using existing pre-trained models
- **Flexibility**: Quickly adapt model behavior for different use cases

**When to use prompt engineering:**
- Building chatbots, virtual assistants, or conversational interfaces
- Creating content generation systems (documentation, FAQs, summaries)
- Extracting structured information from unstructured text
- Building Retrieval-Augmented Generation (RAG) systems
- Prototyping AI applications before investing in custom model training

This workshop teaches you practical prompt engineering techniques using the **LangChain** framework—a popular Python library for building LLM applications—with Groq's free LLM API through hands-on exercises.

![Prompt Engineering Workflow](images/promptengineering-workflow.png)

## Table of Contents
1. [Features](#features)
2. [How It Works](#how-it-works)
3. [Technology Stack](#technology-stack)
4. [Requirements](#requirements)
5. [Installation](#installation)
6. [Configuration](#configuration)
7. [Quick Start](#quick-start)
8. [Usage](#usage)
9. [Project Structure](#project-structure)
10. [Development](#development)
11. [Testing](#testing)
12. [Limitations](#limitations)
13. [License](#license)

## Features

### Prompt Engineering with LangChain
**What it does:**  
Teaches you how to design and refine prompts for Large Language Models using the LangChain framework.

**Why it exists:**  
To provide a practical guide on prompt engineering, focusing on hands-on exercises with real-world examples.

**Why it is useful:**  
Enables users to improve the quality of AI-generated responses by crafting effective prompts without deep model customization.

### Introduction to LangChain
**What it does:**  
Introduces you to the core components and functionalities of the LangChain library.

**Why it exists:**  
To familiarize users with the essential tools and techniques needed for building LLM applications.

**Why it is useful:**  
Equips users with the necessary knowledge to integrate LLMs into their projects efficiently.

## How It Works

The workflow involves several key steps:

1. **User Input/Query**: Your question or request.
2. **Prompt Template**: Structures input with four components:
   - **Instruction**: What the model should do
   - **External Context**: Additional knowledge from documents or databases (source knowledge vs. parametric knowledge)
   - **User Input**: Query dynamically inserted via variables like `{question}`
   - **Output Indicator**: Guides response format (e.g., "Answer:", structured formatting)
3. **Few-Shot Examples**: Example input-output pairs that teach the model your desired format.
4. **LangChain Chain**: Components piped together: `prompt_template | llm | output_parser`.
5. **LLM (Groq API)**: Model (`llama3-8b-8192`) processes the prompt with configurable parameters (`temperature`, `max_tokens`).
6. **Output Parser**: Formats raw responses into usable structures.
7. **Final Response**: Polished output for your application.

This workflow controls LLM behavior without retraining, enabling production-quality results from general-purpose models.

## Technology Stack

| Technology | Purpose |
|------------|---------|
| LangChain  | Python library for building LLM applications. |
| Groq API   | Free LLM API for processing prompts. |
| JupyterLab | Interactive development environment for data science and machine learning projects. |
| python-dotenv | Loads environment variables from a `.env` file. |

## Requirements

- Python 3.11.3 installed (via pyenv)
- Free Groq API key from [Groq Console](https://console.groq.com/playground)
- Basic understanding of Python and Jupyter notebooks

## Installation

To install the required dependencies, run:

```bash
pip install -r requirements.txt
```

## Configuration

The repository includes a `.env` file for environment variables. Ensure you have your Groq API key set up in this file.

## Quick Start

1. **Get your Groq API key**
   - Create a free account at [Groq Console](https://console.groq.com/playground)
   - Copy your API key and add it to the `.env` file under `GROQ_API_KEY`.

2. **Run Jupyter Notebooks**
   - Open the repository in JupyterLab.
   - Execute the cells in `1_intro_langchain.ipynb` for an introduction to LangChain.
   - Proceed to `2_langchain_prompt_engineering.ipynb` for hands-on prompt engineering exercises.

## Usage

To use the LangChain framework with Groq's API, follow these steps:

```python
from langchain import PromptTemplate, LLMChain, FewShotPromptTemplate
from langchain.llms import GroqLLM

# Load environment variables
import os
groq_api_key = os.getenv('GROQ_API_KEY')

# Initialize the LLM with your API key
llm = GroqLLM(api_key=groq_api_key)

# Define a prompt template
prompt_template = PromptTemplate(
    input_variables=["question"],
    template="Answer: {question}"
)

# Create a chain using the prompt template and LLM
chain = LLMChain(llm=llm, prompt=prompt_template)

# Run the chain with a user query
response = chain.run("What is the capital of France?")
print(response)
```

## Project Structure

```plaintext
ds-prompt-engineering/
├── .github/workflows/
│   ├── REGX_test_import_libraries.sh
│   ├── discord-webhook-notify.yml
│   ├── replacement.yml
│   └── workflow-02.yml
├── .gitignore
├── 1_intro_langchain.ipynb
├── 2_langchain_prompt_engineering.ipynb
├── README.md
└── images/
    └── promptengineering-workflow.png
```

## Development

The development workflow involves running the Jupyter Notebooks and using GitHub Actions for continuous integration.

## Testing

No tests are currently available in this repository.

## Limitations

- The example workflows assume a basic understanding of Python and Jupyter notebooks.
- The Groq API key is required to run the examples, which must be obtained from the Groq Console.

## License

This project is licensed under the [MIT License](LICENSE).