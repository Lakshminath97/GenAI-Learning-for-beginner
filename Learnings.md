## Level 1 : Foundations & Prompting
Goal: Undertand the basics of GenAI, LLMs, and become skilled at promt engineering

Table of Contents
---

- [Task 1 : Intro to Gen AI](#what-is-genai)
- [Task 2 : LLMs](#llms-101)
- [Task 3 : Prompting basics](#promting-basics-types-of-promting-and-llm-settings)
- [Task 4 : Prompting practice](#promting-practice)
- [Task 5 : Prompt Templates](#promting-template)
- [Task 6 : Advanced Prompting](#advanced-prompting)
- [Task 7 : Project 1 - Prompt Crafting](#prompt-crafting)

---

## **What is GenAI?**

Gen AI produces original contents based on things learned on large datasets and algorithms based on user prompts

### Steps in Gen AI:

1. Data collection and learning 
2. ⁠neural networks and transformers 
    (Transformer models process text and recognises text )
3. Tokens and contexts 
    (The prompt or text is split into tokens and AI recognises or process and understand relationship to create accurate result )
4. Feedback mechanism 
    (Feedback from user)
5. Reinforcement learning 
    (Based on feedback/ positive reinforcement  to reinforce the ai ability to improve the models)
6. Data science and AI models 
    (Data scientist curate the AI models to make it more efficient, train AI models with data sets )
7.  Generating original content 
    (A unique image produced based on things learned)

### Block Diagram :
<img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/b54cfd2b-d495-446a-9873-eb35a399eca6" />

## **LLMs 101** 
[Transformer architecture, pretraining vs fine-tuning, tokens, context window]

### Transformers 
- Transforms from one sequence to another 
- Two parts- encoder and decoder 

* Encoder looks into input 
* Decoder to output 
For example: transformer works in sequence to sequence learning
It takes sequence of word in a sentence and predicts next words 
It works through iterating encoding layers, encoder generates encodings to find which part of input sequence is related to each other and then passes to next encoding layer 
Decoder takes this encodings or encoding layer and generates output sequence

### Pretraining and fine tuning 
Transformer are part of semi supervised learning or pre-training in unsupervised manner 
And fine tuned to perform in supervised Manner 

* Pretraining in general refers to training a base model with set of data sets and thus learns the context of data sets 

* Fine tuning - tuning whole part or training pre training model to train for a specific task

#### Attention mechanism

Transformers has something called attention mechanism 

Attention mechanism provide context around other words in the input 
Which helps transformer to run multiple sequence in parallel

Three main innovation 
- Positional encoding ( store the word order as a numbers ) 
- ⁠attention 
- ⁠self attention (Allows neural network to understand word in context of words around it)

### RNN - recurrent neural network
It take a sentence as input and process one by one 
It has a downside that only one word at a time, so long paragraph cannot be processed as it cannot run in a parallel

### Context window
The context window is the number of tokens the model can “remember” at once.
Context windows measured in tokens( smallest unit of measurement for a AI model)

### Token
Can be a part of word, a single character or whole word 
- Tokeniser - converts a language to tokens 
A word in English lang has assigned - 1.5tokens

### Context window
Context window size rapidly increasing (thousands of tokens)

Lot of thing taking space in context window 
1. User inputs
2. ⁠model response 
3. ⁠System prompt ( this is often hidden from user, this condition behaviour of AI model) 
4. ⁠Documents uploaded by users 
  5.Code uploaded by users 
  6.Supplementary information drawn from external day sources called RAG ( retrieval augmented generation) 

But the larger context windows provide challenges
1. Compute time 
2. ⁠takes up space 
3. ⁠effect performance

## **Promting basics, Types of promting and LLM settings**
<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/e1052c9a-3f8b-4dd8-bb11-4bd494514019" />

## **Promting practice**
Use OpenAI Playground/ChatGPT/Claude: Play with prompts

🧪 Prompting Exercises (Beginner to Intermediate)

📌 1. Role-Based Prompting
📝 Prompt:
“You are a career coach. Give me 3 suggestions to improve my resume for a software engineering job.”

🎯 Goal: Test how the assistant changes tone, depth, and advice depending on the assigned role.

👉 Variation:

Change “career coach” to “HR manager” or “hiring manager at Google.”

📌 2. Instruction vs Chat
📝 Prompt 1 (Instruction):
“Summarize the paragraph below in 2 bullet points.”
Then paste some long text.

📝 Prompt 2 (Chat):
“I just read this long article but don’t have time to go through all of it. Can you explain the key points in simple terms?”

🎯 Goal: See how the model changes response between direct command and conversational tone.

📌 3. Chain-of-Thought Prompting
📝 Prompt:
“If Sam has 2 red balls and 3 green balls, and gives away 1 red and 2 green balls, how many are left? Think step by step.”

🎯 Goal: Trigger reasoning by using “Think step by step.”

👉 Try without that phrase and compare.

📌 4. Creative Prompting
📝 Prompt:
“Write a bedtime story about a lonely asteroid that becomes friends with a comet. Make it poetic and under 150 words.”

🎯 Goal: Stimulate the model’s creativity and tone control.

👉 Variation: “Make it a Shakespearean play” or “Write it like a Reddit story.”

📌 5. Prompt Compression
📝 Prompt:
Give a very long paragraph (e.g., Wikipedia article). Then ask:
“Summarize this in 1 sentence.”
“Now in 5 words.”
“Now using only emojis.”

🎯 Goal: Explore how LLMs compress information.

📌 6. Bias Detection
📝 Prompt:
“Describe a doctor.”
“Describe a nurse.”
“Describe a CEO.”

🎯 Goal: Observe and identify implicit societal biases in LLMs and learn to write neutral prompts.

📌 7. Prompt Rewriting
📝 Prompt:
“Rewrite the following prompt to improve clarity and structure for an AI system:
‘Help me with Java problems.’”

🎯 Goal: Learn how to engineer better prompts by rewriting vague ones.

📌 8. Prompt Temperature Testing (in Playground)
Use the same prompt, e.g.,
“Write a tweet about AI for beginners.”
Try temperatures 0.2, 0.7, and 1.0.

🎯 Goal: Understand randomness and creativity control using temperature.



## **Promting template**

### Instructional prompt 
Structure : 
action ( what to be done), format ( how should it present), constrain ( what rules to be followed)

![WhatsApp Image 2025-08-17 at 22 24 02](https://github.com/user-attachments/assets/e34a0ec2-dea3-41ec-995f-f516d7f8fcce)

![WhatsApp Image 2025-08-17 at 22 24 02 (1)](https://github.com/user-attachments/assets/83e45ad9-f12a-4e2c-ae3e-18df0cd0009b)

Common mistake to avoid
- Being too vague ( too simple) 
- Overloading output ( too complex) 
- Forgetting audience 
- ⁠too ambiguous 
- ⁠not reviewing output

### Role based prompt 

Prompting based on role 
Structure : 
1. Assign the role (like coach)
2. ⁠define the task (help switch to data science)
3. ⁠add style tone or constrain (in simple way)

<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/ec82d75e-ca08-469b-8a7b-961174ee3e3e" />

<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/0e54a61b-9e42-4bd8-b6af-2077476e2ed1" />

Common mistake to avoid 
1. Vague roles 
2. ⁠mismatched roles
3. ⁠no task given 
4. ⁠Ignoring tones or styles

## **Advanced Prompting**
ReAct promting, self ask, tree-of-thought (ToT)

## Prompt crafting
Build a promt based mini tool (eg. resume critic or email writer)



## 📚 Topics I’m Learning
- Python basics  
- NX Open API with C#  
- Machine learning fundamentals  

## 🎯 Goals
