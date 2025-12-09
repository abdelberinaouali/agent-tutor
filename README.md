# AI Research Assistant

A LangChain-powered AI research assistant that helps generate research papers by searching the web and Wikipedia, then saving structured results.

## Overview

This project creates an intelligent agent that can:
- Search the web using DuckDuckGo
- Query Wikipedia for information
- Generate structured research responses
- Save results to text files with timestamps

## Features

- **Web Search**: Integrated DuckDuckGo search for current information
- **Wikipedia Search**: Access to Wikipedia articles for research
- **Structured Output**: Pydantic-based response formatting
- **File Saving**: Automatic timestamped research output
- **Tool Calling**: LangChain agent framework for intelligent tool usage

## Requirements

- Python 3.8+
- Anthropic API key (for Claude 3.5 Sonnet)
- Environment variables configured

## Installation

1. Clone the repository
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up environment variables:
   ```bash
   # Create .env file with your Anthropic API key
   ANTHROPIC_API_KEY=your_api_key_here
   ```

## Usage

Run the main application:
```bash
python main.py
```

Enter your research query when prompted. The agent will:
1. Analyze your query
2. Use appropriate tools (search, Wikipedia)
3. Generate a structured response
4. Optionally save results to file

## Project Structure

```
AI Agent Tutorial/
├── main.py              # Main application and agent setup
├── tools.py             # Tool definitions (search, Wikipedia, save)
├── requirements.txt     # Python dependencies
├── .env                # Environment variables (API keys)
└── README.md           # This documentation
```

## Components

### main.py
- Sets up LangChain agent with Claude 3.5 Sonnet
- Defines Pydantic response model
- Handles user interaction and response parsing

### tools.py
- **search_tool**: DuckDuckGo web search
- **wiki_tool**: Wikipedia article search
- **save_tool**: File saving with timestamps

## Response Format

The agent returns structured responses with:
- `topic`: Research topic
- `summary`: Generated summary
- `sources`: List of sources used
- `tools_used`: Tools utilized in research

## Dependencies

- `langchain`: Core framework
- `langchain-anthropic`: Anthropic integration
- `langchain-community`: Community tools
- `python-dotenv`: Environment variable management
- `pydantic`: Data validation
- `duckduckgo-search`: Web search functionality
- `wikipedia`: Wikipedia API access

## Example

```python
# User input: "Tell me about quantum computing applications"

# Agent response:
ResearchResponse(
    topic="quantum computing applications",
    summary="Quantum computing has applications in cryptography, drug discovery, financial modeling, and optimization problems...",
    sources=["https://example.com/quantum-apps", "https://en.wikipedia.org/wiki/Quantum_computing"],
    tools_used=["search", "wiki"]
)
```

## Contributing

Feel free to extend the project with additional tools or improve the agent's capabilities.