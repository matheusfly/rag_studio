# Simple RAG with LLM Studio

This project demonstrates a simple retrieval-augmented generation (RAG) application using LLM Studio. It allows you to interact with your LLM Studio model through a Gradio chat interface, providing context-aware responses based on a knowledge base.

## Setup

1. **Install Poetry:** If you don't have Poetry installed, run:
   ```bash
   pip install poetry

2. Create a Virtual Environment:

```python
poetry env use .venv  # Use a specific virtual environment name if desired
poetry install
```

3. Set Environment Variables:

- OPENAI_API_KEY: Your OpenAI API key.
- LLM_STUDIO_API_BASE: The endpoint of your LLM Studio server (e.g., http://localhost:1234/v1).
    
    You can set these variables in your shell environment or within your code.

## Running the Application

1. Start LLM Studio: Ensure your LLM Studio server is running.
2. Run the Script: Execute the main Python script:

'''shell
python rag_studio/main.py


This will launch a Gradio chat interface in your web browser.

## Usage
1. Ask Questions: Type your questions into the chat interface.

2. Get Context-Aware Responses: The application will retrieve relevant context from its knowledge base and use it to generate responses from your LLM Studio model.

3. View Sources: The chat interface will display the sources used to generate the response.

# Explanation

## Core Components
- LLM: The LLM Studio model you're using for text generation.
- Embeddings: A model that converts text into numerical representations (embeddings).
- Vector Store: A database that stores the embeddings of your knowledge base, allowing for efficient similarity search.
- Retriever: A component that retrieves relevant context from the vector store based on user queries.
- RetrievalQA Chain: A LangChain chain that combines the retriever and LLM to generate responses.

## Key Steps

1. Import Libraries: Import necessary libraries for LLM, embeddings, vector stores, and Gradio.
2. LLM Configuration: Configure the LLM by setting the openai_api_base and openai_api_key variables.
3. Prompt Template: Define a prompt template for the LLM, including context and user question.
4. Text Wrapping: Define a function to wrap text for better readability in the chat interface.
5. LLM Response Processing: Define a function to process the LLM response, including extracting the answer and displaying sources.

6. Start Chat Function:

    Create an embedding model (e.g., HuggingFaceBgeEmbeddings).
    Create a vector store (e.g., Chroma) to store your knowledge base.
    Define a retriever to fetch relevant context from the vector store.
    Create a RetrievalQA chain to combine the retriever and LLM.
    Define a runChain function to handle user queries and return responses.
    Create a Gradio ChatInterface to display the chat interface.
    Launch the Gradio interface.

## Customization
- Knowledge Base: You can customize the knowledge base by adding or modifying documents in the content/chroma_db directory.
- Embedding Model: Experiment with different embedding models to find the best fit for your knowledge base.
- Prompt Template: Adjust the prompt template to fine-tune the LLM's behavior.
  
  - Example

´´´´shell
User: What is the capital of France?
Response: The capital of France is Paris.

Sources:
- Wikipedia: https://en.wikipedia.org/wiki/Paris
´´´´

### Conclusion
This project provides a basic framework for building RAG applications using LLM Studio. You can extend it by adding more features, such as:

    - Multi-turn conversations: Allow the application to remember previous interactions.
    - Advanced retrieval: Implement more sophisticated retrieval strategies.
    - Custom LLM models: Integrate other LLM models besides OpenAI.
    - User authentication: Secure access to the application.
    - This project is a starting point for exploring the power of RAG and LLM Studio. Feel free to experiment and customize it to suit your specific needs.


**Remember to replace the placeholders with your actual values.**

This README.md provides a comprehensive documentation for your project, including setup instructions, usage guide, explanation of the code, and customization options. It also includes an example interaction and suggestions for further development.
