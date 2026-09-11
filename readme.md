Document Management System Using RAG

Step 1:

    Loading each document data into a "Document Data Structure" using Langchain's Document data structure

Step 2:

    Documents are converted into multiple chunks using Semantic Chunker for getting better chunks.

    Can also use Recursive Character text splitter specifying chuk size, chunk overlap, class of document loader and seperators(i.e " ", \n, etc)

Step 3:

    Create a vector store like Chroma DB , FAISS, Inmemory Vector Store to store the page content of each chunk in the form of embeddings.

    Use Open AI Embedding Model like "text-embedding-3-small" or "text-embedding-3-large" for converting text into embeddings.

    Can also use Hugging Face open source models or Groq open source models for embedding purpose.

Step 4:

    Define a custom prompt using ChatPromptTemplate or any other template function of langchain.

    Custom Prompt will consist of system instruction & human input

    Can also create a Conversational Memory using history aware retriever of langchain that helps the LLM to memorize the previous interaction and helps it remembering the previous chats.

Step 5:

    We convert our vector store into retriever

    Then we combine the LLM & Prompt using document chain

    Document Chain stuffs all the relevant documents returned by the retriever according to the user query inside the context placeholder of the prompt & then the prompt is given to the LLM.

    We can use Open AI, Hugging Face, Groq LLMs according to the requirement of the system.

Step 6:

    Finally, we combine retriever & document chain using retrieval chain of langchain.

     By using invoke function, we can ask question to the LLM regarding any topic in the uploaded documents and it will give us a satisfying answer.