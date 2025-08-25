## APIs, Tools & Fine Tuning
Goal: Undertand the basics of GenAI, LLMs, and become skilled at promt engineering

Table of Contents
---



---
## Task 8: Understand Basics
---
- What is an API? (It’s like a waiter between your app and OpenAI)
- What is an LLM? (Large Language Model – ChatGPT is one)
- Why use LangChain? (It lets you chain multiple AI steps together like building blocks)

Activity:
Watch a 5 min YouTube video on “What is an API?” and “What is OpenAI?”


## Task 9: Environment Setup
---
- Install Python
Download and install Python 3.10+ from python.org

- Install VS Code (or use Google Colab for zero setup)
Install Required Tools
```bash
pip install openai
pip install langchain
pip install python-dotenv  # For managing API keys 
```

- Get OpenAI API Key / Open Router Key

Sign up at https://platform.openai.com #For OpenAI API  
Go to API Keys, generate a key, and save it.

Sign up at https://openrouter.ai/models #For OpenRouter API  
Go to Keys, generate a key, and save it

## Task 10: Call OpenRouter API

- First OpenRouter API Call

```python
import requests #Lets you make HTTP requests (like GET, POST) to talk to APIs.
import json #Lets you convert Python data (like dictionaries) to JSON format and vice versa.

response = requests.post(
  url="https://openrouter.ai/api/v1/chat/completions",
  headers={
    "Authorization": "Bearer OpenRouter key",
    "Content-Type": "application/json", #Tells the API that you’re sending data in JSON format
  },
  data=json.dumps({ 
    "model": "tngtech/deepseek-r1t2-chimera:free", #can use any suitable model 
    "messages": [
      {
        "role": "user",
        "content": "What is the meaning of life?"
        
      }
    ],
    "max_tokens": 500
  })
)
```
Task:
Change the role, content and max_tokens and observe the change  


