# 🧒     Chatbot-Text-to-Text-QA-for-Kids

> Making Python Programming Accessible, Fun, and Friendly for Kids Aged 8–12

---

## 📘 Introduction

Digital literacy and programming skills are becoming essential for the next generation. However, most programming resources use technical language that can overwhelm young learners aged 8–12. This project addresses that gap by developing a **child-friendly Python programming assistant** that explains coding concepts in simple, accessible ways.

---

## ❓ Problem Statement

The primary challenges in teaching programming to children include:

- 🧠 Technical terminology that is difficult to understand  
- 📚 Lack of age-appropriate explanations  
- 🧸 Need for relatable, real-life examples  
- 🎮 Limited resources that are engaging and confidence-building  

---

## 💡 Solution Approach

We implement a **Retrieval-Augmented Generation (RAG)** system designed specifically for children's Python education.

### Our System:
1. 📥 Retrieves relevant information from curated, trusted Python resources  
2. 🧽 Simplifies and processes the content for children's comprehension level  
3. ✏️ Generates easy explanations with examples  
4. 🎉 Uses encouraging and positive language  

RAG ensures factually correct responses while being kid-friendly and understandable.

---

## ⚙️ Technical Implementation

### 🗂️ Data Collection

- **Sources:**  
  - [Programiz.com](https://programiz.com)  
  - Official Python documentation  
- **Methods:** Web scraping using `requests` and `BeautifulSoup` (for HTML) and custom PDF handlers  
- **Scope:** Core topics like variables, data types, conditions, loops  
- **Size:** 50,726 words from 5 documents

### 🔧 Text Preprocessing

- **Cleaning:** Removing irrelevant text, standardizing format  
- **Chunking:** Recursive Text Splitter  
  - Chunk size: 500 words  
  - Overlap: 100 words  
  - Structure-aware splitting (paragraph → sentence → word)  
- **Output:**  
  - ✅ 1,064 clean, semantically coherent text chunks  
  - 🧾 Metadata: URL, title, chunk ID, word count

### 🔎 Vector Embedding

- **Model Used:** `all-MiniLM-L6-v2` (via SentenceTransformers)  
- **Embedding Dimension:** 384  
- **Validation:** Batched embedding with sample checks

### 🧠 Vector Database

- **Backend:** ChromaDB (in-memory vector DB)  
- **Metadata Included:**  
  - Document ID  
  - Full chunk text  
  - URL, Title  
  - Word count and vector  
- **Functionality:** Fast semantic similarity search

### 🤖 Question Answering System (RAG)

- **Step 1: Embedding User Query**  
  - Same encoder as for the documents  
- **Step 2: Retrieval**  
  - Fetch top 3–5 relevant text chunks  
- **Step 3: Context Preparation**  
  - Formatted input to the language model  
- **Step 4: Answer Generation**  
  - **Model:** `mistral-small` via [Mistral AI API](https://docs.mistral.ai)  
  - **Prompting:**  
    - Simple, age-appropriate  
    - Friendly and supportive  
    - Based **only** on retrieved context  
    - Examples included when helpful  
  - **Params:** Temperature = 0.5, Max Tokens = 500  
  - **Fallback Handling:** Graceful error messages for failed calls

---

## 🧪 Example Interactions

| Question | Child-Friendly Answer Summary |
|---------|-------------------------------|
| **"what is while loop in python?"** | ![image](https://github.com/user-attachments/assets/1524b666-fbee-41ea-8dd0-066e547fa6be)
 |
| **"what is if conditions in python?"** | ![image](https://github.com/user-attachments/assets/c2c1eb8b-4c8a-4778-9d12-0a46bf9c0502)
 |
| **"what is variable meaning in python?"** | ![image](https://github.com/user-attachments/assets/5452980d-688e-40c8-8515-e4b783f5409c)
 |
| **"what is types of numbers in python?"** | ![image](https://github.com/user-attachments/assets/667c3f89-f135-4116-bbe4-e257a08b96a9)
 |
| **"how to loop in python?"** | ![image](https://github.com/user-attachments/assets/b2846d4e-9ed4-4345-93b3-27958d284fb0)
 |

---

## ✅ Conclusion

This project successfully achieves its goal of making programming education accessible to children by:

- 🧒 Translating complex concepts into **simple, kid-friendly** language  
- ✍️ Providing **relatable examples**  
- 🎈 Using **encouraging words** to build confidence  
- 📚 Ensuring **accuracy** through reliable sources and RAG-based generation

---


