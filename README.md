# ChatApp_Llama-2-7B-Chat-GGUF
![image](https://github.com/shivamkapoor172002/ChatApp_Llama-2-7B-Chat-GGUF/assets/92868323/80a9420f-d811-40e5-8333-6f6551ccdf9b)

# Chatbot Deployment with Streamlit

This repository contains the code for deploying a chatbot using Streamlit. The chatbot is powered by the Llama-2-7B language model.

## Deployment Steps

1. Install the required Python packages:

    ```bash
    !pip install -qq langchain wget llama-index cohere llama-cpp-python
    ```

2. Download the Llama-2-7B model:

    ```python
    import wget

    def bar_custom(current, total, width=80):
        print("Downloading %d%% [%d / %d] bytes" % (current / total * 100, current, total))

    model_url = "https://huggingface.co/TheBloke/Llama-2-7B-Chat-GGUF/resolve/main/llama-2-7b-chat.Q2_K.gguf"
    wget.download(model_url, bar=bar_custom)
    ```

3. Install Streamlit:

    ```bash
    !pip -q install streamlit
    ```

4. Uncomment the code in `app.py` to set up the Streamlit app:

    ```python
    import streamlit as st
    from llama_index import (
      SimpleDirectoryReader,
      VectorStoreIndex,
      ServiceContext,
    )
    # ... (rest of the code)

    if __name__ == "__main__":
      main()
    ```

5. Run the Streamlit app and expose it with localtunnel:

    ```bash
    !streamlit run app.py & npx localtunnel --port 8501
    ```

## Usage

1. Input your question in the chat interface.
2. The chatbot will respond with an answer in markdown format.

## Additional Notes

- The Llama-2-7B model is downloaded from the Hugging Face model hub.
- The Streamlit app is configured to interact with the Llama-2-7B model to provide responses to user queries.

Feel free to explore and modify the code to suit your specific use case!
