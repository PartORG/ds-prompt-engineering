# Prompt Engineering with LangChain

**Prompt engineering** is the practice of designing and refining inputs (prompts) to guide Large Language Models (LLMs) toward producing desired outputs. Well-crafted prompts can dramatically improve the quality, accuracy, and relevance of AI-generated responses.

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

## Features

### Dynamic Prompt Templates
- **Instruction**: What the model should do
- **External Context**: Additional knowledge from documents or databases (source knowledge vs. parametric knowledge)
- **User Input**: Query dynamically inserted via variables like `{question}`
- **Output Indicator**: Guides response format (e.g., "Answer:", structured formatting)

### Few-Shot Examples
Example input-output pairs that teach the model your desired format.

### LangChain Chain
Components piped together: `prompt_template | llm | output_parser`

### Configurable LLM Parameters
Model (`llama3-8b-8192`) processes the prompt with configurable parameters (`temperature`, `max_tokens`).

### Output Parser
Formats raw responses into usable structures.

## How It Works

The workflow controls LLM behavior without retraining, enabling production-quality results from general-purpose models.

1. **User Input/Query** - Your question or request
2. **Prompt Template** - Structures input with four components:
   - **Instruction**: What the model should do
   - **External Context**: Additional knowledge from documents or databases (source knowledge vs. parametric knowledge)
   - **User Input**: Query dynamically inserted via variables like `{question}`
   - **Output Indicator**: Guides response format (e.g., "Answer:", structured formatting)
3. **Few-Shot Examples** - Example input-output pairs that teach the model your desired format
4. **LangChain Chain** - Components piped together: `prompt_template | llm | output_parser`
5. **LLM (Groq API)** - Model (`llama3-8b-8192`) processes the prompt with configurable parameters (`temperature`, `max_tokens`)
6. **Output Parser** - Formats raw responses into usable structures
7. **Final Response** - Polished output for your application

## Technology Stack

| Technology | Purpose |
|------------|---------|
| LangChain  | Popular Python library for building LLM applications |
| Groq API   | Free LLM API for general-purpose models |
| JupyterLab | Interactive development environment for notebooks |
| python-dotenv | Loads environment variables from a `.env` file |

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

Ensure you have a `.env` file with your Groq API key:

```plaintext
GROQ_API_KEY=your_groq_api_key_here
```

## Quick Start

1. **Get your Groq API key**
   - Create a free account at [Groq Console](https://console.groq.com/playground)
2. **Clone the repository**
   ```bash
   git clone https://github.com/PartORG/ds-prompt-engineering.git
   cd ds-prompt-engineering
   ```
3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```
4. **Run Jupyter notebooks**
   ```bash
   jupyter lab 1_intro_langchain.ipynb
   ```

## Usage

### Notebook 1: LangChain Fundamentals
- What LangChain is and its core components (prompts, LLMs, chains, tools, agents, memory)
- How to integrate LLMs (specifically Groq's API) with LangChain
- How to create prompt templates with dynamic input variables
- How to build chains by piping components together (`prompt | llm`)
- How to invoke chains for single and batch queries

### Notebook 2: Prompt Engineering Techniques
- Applying the 4-part prompt structure in practice
- Context-based question answering with external knowledge
- Few-shot prompting with example input-output pairs
- Using `FewShotPromptTemplate` to structure examples systematically
- Chaining with output parsers for formatted responses

## Project Structure

```
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
├── images/
│   └── promptengineering-workflow.png
└── requirements.txt
```

## Development

The development workflow involves running the Jupyter notebooks and making changes to the code. Ensure you have a `.env` file with your Groq API key.

## Testing

No tests are currently available for this project.

## Limitations

- The workshop assumes familiarity with Python and Jupyter notebooks.
- The use of Groq's free API may have limitations on request rates.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.