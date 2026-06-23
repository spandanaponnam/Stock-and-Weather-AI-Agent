# AI Agent Application

A Python based AI Agent application that can understand user queries, decide the required action, use available tools, and return a response.

The project uses an LLM model with custom tools for:

- Weather information
- Stock market data
- System command execution

The application also provides a simple web interface using Streamlit.

---

## Project Overview

This project demonstrates how an AI agent works with external tools.

Instead of only generating text, the agent can:

1. Understand the user request
2. Decide whether a tool is required
3. Call the required function
4. Process the returned data
5. Provide the final response

Agent workflow:

```
User Input
    |
    v
Agent
    |
    +------------+
    |            |
 Tool Needed?   No Tool
    |
    v
Execute Function
    |
    v
Get Result
    |
    v
Generate Response
```

---

## Features

- AI powered chat assistant
- Tool based agent architecture
- JSON based agent communication
- Weather API integration
- Stock price lookup
- Command execution support
- Streamlit user interface
- Conversation history support

---

## Technologies Used

- Python
- OpenAI SDK
- Streamlit
- Requests
- Python dotenv
- REST APIs

---

## Project Structure

```
AI-Agent/
│
├── agent.py
│
├── app.py
│
├── requirements.txt
│
├── .env
│
└── README.md
```

---

## File Description

### agent.py

Contains the main AI agent logic.

Responsibilities:

- Connects with the LLM API
- Handles user prompts
- Creates the agent loop
- Executes tools
- Returns final responses

---

### app.py

Contains the Streamlit application.

Responsibilities:

- Creates chat interface
- Displays conversation
- Sends user input to the agent
- Shows responses

---

## Agent Workflow

The agent follows this process:

```
Plan
 |
 v
Action
 |
 v
Observation
 |
 v
Output
```

Example:

User:

```
What is Tesla stock price?
```

Agent decides:

```
Tool required
```

Then calls:

```
get_stock_data("TSLA")
```

The result is returned and displayed.

---

# Available Tools

## Weather Tool

Function:

```
get_weather(city)
```

Example:

```
Weather in Hyderabad
```

The agent sends:

```
get_weather("Hyderabad")
```

---

## Stock Data Tool

Function:

```
get_stock_data(symbol)
```

Examples:

```
Tesla  -> TSLA
Apple  -> AAPL
Microsoft -> MSFT
Infosys -> INFY
```

Example query:

```
What is Apple stock price?
```

The agent converts it:

```
AAPL
```

and fetches the data.

---

## Command Tool

Function:

```
run_command(command)
```

Used for executing system commands.

Example:

```
Show files
```

Possible execution:

Linux:

```
ls
```

Windows:

```
dir
```

---

# Installation

## Clone Repository

```
git clone <repository-url>

cd AI-Agent
```

---

## Create Virtual Environment

Windows:

```
python -m venv venv

venv\Scripts\activate
```

Linux / Mac:

```
python3 -m venv venv

source venv/bin/activate
```

---

## Install Dependencies

Run:

```
pip install -r requirements.txt
```

---

## Requirements

Create `requirements.txt`

```
openai
python-dotenv
requests
streamlit
```

---

# Environment Setup

Create a file named:

```
.env
```

Add required keys:

```
API_KEY=your_api_key
```

---

# API Configuration

Update your model configuration in `agent.py`.

Example:

```python
client = OpenAI(
    base_url="YOUR_API_BASE_URL",
    api_key="YOUR_API_KEY"
)
```

Add your model details.

---

# Run Application

Start the Streamlit server:

```
streamlit run app.py
```

Open in browser:

```
http://localhost:8501
```

---

# Example Queries

Weather:

```
Weather in London
```

Stocks:

```
Tesla stock price
```

```
Microsoft stock price
```

Commands:
```
List files
```
# Security Note
The command execution feature can run system commands.
For production usage:
- Restrict allowed commands
- Add authentication
- Run inside a sandbox
- Limit permissions
# Future Improvements

Possible enhancements:

- Add more APIs
- Add memory support
- Add database connection
- Add authentication
- Add voice support
- Deploy using Docker
- Add more AI tools

---

## License

This project is for learning and development purposes.
