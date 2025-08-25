## APIs, Tools & Fine Tuning
Goal: Use GenAI APIs and understand how to fine-tune small models

Table of Contents
---

- [Task 8 : Basics](#understand-basics)
- [Task 8 : Setting up Environment](#environment-setup)
- [Task 9 : Call API](#first-openrouter-api-call)
- [Task 10 : LangChain](#what-is-langchain)

---
## **Task 8: Understand Basics**

- What is an API? (It’s like a waiter between your app and OpenAI)
- What is an LLM? (Large Language Model – ChatGPT is one)
- Why use LangChain? (It lets you chain multiple AI steps together like building blocks)

Activity:
Watch a 5 min YouTube video on “What is an API?” and “What is OpenAI?”

---

## **Environment Setup**

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

---

## **First OpenRouter API Call**

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

### JSON
JSON stands for JavaScript Object Notation.  
It’s a way to store and send data that’s:
-Easy for humans to read
-Easy for computers to understand  

Think of it like a digital notebook where you write information in a key-value pair style.
---

## 🔗What is LangChain?

LangChain is an open-source framework for building applications with Large Language Models (LLMs).  
It extends LLMs beyond text generation by adding:

- **Prompt templates** – reusable & dynamic prompts  
- **Chains** – link multiple steps (LLM calls, APIs, custom logic)  
- **Agents** – LLMs that choose tools/actions dynamically  
- **Memory** – maintain context across interactions  
- **Data/tool integration** – connect LLMs to databases, APIs, search, and vector stores  

💡 Use cases: chatbots, document Q&A, automation agents, and AI assistants.

### Install LangChain
```bash
pip install langchain
pip install openai
```
### First LangChain Example
```python
from langchain_openai import ChatOpenAI
from langchain_core.messages import HumanMessage
import os


# Your OpenRouter API key
OPENROUTER_API_KEY = "KEY"
# Setup ChatOpenAI with OpenRouter
chat = ChatOpenAI(
    model="mistralai/mistral-7b-instruct:free",
    openai_api_key=OPENROUTER_API_KEY,
    openai_api_base="https://openrouter.ai/api/v1",
    temperature=0.7
)
# Define the prompt
messages = [HumanMessage(content="What is the meaning of life?")]

# Use .invoke() for latest LangChain usage
response = chat.invoke(messages)

print(response.content)

```
### Chain Two LLMs
```python
openai_api_base = "https://openrouter.ai/api/v1"
openai_api_key=OPENROUTER_API_KEY

#Inheriting
def call_openai(model, temperature):
    return ChatOpenAI(
    model=model,
    openai_api_key=openai_api_key,
    openai_api_base=openai_api_base,
    temperature=temperature,
    )

#Main Function   
from langchain_openai import ChatOpenAI
from langchain.chains import LLMChain, SimpleSequentialChain
from langchain.prompts import PromptTemplate


# Your OpenRouter API key
OPENROUTER_API_KEY = "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"
# Setup ChatOpenAI with OpenRouter
chat1 = call_openai(model="mistralai/mistral-7b-instruct:free", temperature=0.7)
chat2 = call_openai(
    model="mistralai/mistral-7b-instruct:free",
    temperature=0.5
)

prompt1 = PromptTemplate(
    input_variables=["topic"],
    template="List 3 key points about the topic: {topic}"
)

prompt2 = PromptTemplate(
    input_variables=["points"],
    template="Expand the following points into a short paragraph:\n{points}"
)

print(f'PromptTemplate is here \n {prompt1} \n')

chain1 = LLMChain(llm=chat1, prompt=prompt1)
print(chain1)
chain2 = LLMChain(llm=chat2, prompt=prompt2)

overall_chain = SimpleSequentialChain(
    chains=[chain1, chain2],
    verbose=True  # Optional: shows intermediate steps
)

# Run the chain
output = chain1.run("Artificial Intelligence")
print(output)

```
