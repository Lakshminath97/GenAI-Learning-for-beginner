# GenAI-Learning-for-beginner
GenAI learning journey - This repo contains my personal learning notes and practice code as i explore GenAI 

# My Learning Journey 🚀
Hi! This repo is where I document everything I’m learning.  
I use it as a personal knowledge base and for sharing with others.

## 📅 Daily / Weekly Logs

**Week 1**
# Topics covered

**Day 1:** What is GenAI, LLMs, use cases (text, image, code), models (GPT, Claude, LLaMA)

*Day1: What is Gen AI?
Gen AI produces original contents based on things learned on large datasets and algorithms based on user prompts

Steps in Gen AI:
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

Block Diagram : 
<img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/b54cfd2b-d495-446a-9873-eb35a399eca6" />

**Day 2:** LLMs 101 [Transformer architecture, pretraining vs fine-tuning, tokens, context window]

****Transformers 
- Transforms from one sequence to another 
- Two parts- encoder and decoder 

Encoder looks into input 
Decoder to output 
For example: transformer works in sequence to sequence learning
It takes sequence of word in a sentence and predicts next words 
It works through iterating encoding layers, encoder generates encodings to find which part of input sequence is related to each other and then passes to next encoding layer 
Decoder takes this encodings or encoding layer and generates output sequence

****Pretraining and fine tuning 
Transformer are part of semi supervised learning or pre training in unsupervised manner 
And fine tuned to perform in supervised Manner 

Pretraining in general refers to trainign a base model with set of data sets and thus learns the context of data sets 

Fine tuning - tuning whole part or training pre training model to train for a specific task

Transformers has something called attention mechanism 

Attention mechanism provide context around other words in the input 
Which helps transformer to run multiple sequence in parallel

Three main innovation 

- Positional encoding ( store the word order as a numbers ) 
- ⁠attention 
- ⁠self attention (Allows neural network to understand word in context of words around it)

****RNN - recurrent neural network
It take a sentence as input and process one by one 
It has a downside that only one word at a time, so long paragraph cannot be processed as it cannot run in a parallel

****Context window
The context window is the number of tokens the model can “remember” at once.
Context windows measured in tokens( smallest unit of measurement for a AI model)

****Token
Can be a part of word, a single character or whole word 
- Tokeniser - converts a language to tokens 
A word in English lang has assigned - 1.5tokens

****Context window
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

**Day 3:** Promting basics, Types of promting and LLM settings
<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/e1052c9a-3f8b-4dd8-bb11-4bd494514019" />

**Day 4:** Promting practice
Use OpenAI Playground/ChatGPT/Claude: Play with prompts

**Day 4:** Promting template

1. Instructional prompt 
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

## 📚 Topics I’m Learning
- Python basics  
- NX Open API with C#  
- Machine learning fundamentals  

## 🎯 Goals

