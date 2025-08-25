## How I Built It
### 1. The Tools
I used the following tools:
- **LLM (The Brain):** Groq API with the `llama3-8b-8192` model. It's super fast and powerful!
- **Vector Database (The Filing Cabinet):** ChromaDB. It's easy to use and perfect for beginners like myself who have just started learning about RAG.
- **Embeddings (The Magic Translator):** The `all-MiniLM-L6-v2` model from SentenceTransformers to turn text into numbers.

### 2. The Process
1.  **Dataset:** I created my own list of 22 fun facts to avoid any copyright issues.
2.  **Embeddings:** My code takes each fact and converts it into a mathematical vector (a list of numbers) that represents its meaning.
3.  **Storage:** These vectors are stored in the ChromaDB database.
4.  **Retrieval:** When I ask a question, it is first converted into a vector. ChromaDB finds the fact whose vector is most similar to my question's vector.
5.  **Generation:** This retrieved fact is sent to the Groq API with instructions to answer my question using ONLY that particular fact most relevant to the question.

> **Note on the Model:** I initially tried using the `mixtral-8x7b-32768` model, but found that Groq's API suggested using `llama3-8b-8192` as a supported alternative. I updated my code to use this model, and it worked perfectly! This shows how important it is to be flexible and use the tools that are available and working.

## How to Run This Project
1.  Get a free API key from [Groq](https://console.groq.com/).
2.  Open the `first_RAG_project.ipynb` notebook in **Google Colab**.
3.  Upload the `requirements.txt` file to Colab (use the file upload icon in the left sidebar).
4.  Run the first cell to install the libraries.
5.  **When you run the second cell, a box will appear.** Paste your Groq API key there (Don't worry the text will be hidden) and press Enter.
6.  Run the remaining cells one by one to see the magic happen! Happy Learning !

**Warning: Never share your API key or upload it to GitHub!**
