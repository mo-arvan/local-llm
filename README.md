# Local Llama-2 

This repository contains docker-compose file for running Llama-2 locally. I have tested this on Linux using NVIDIA GPUs (Driver 535.86.05, CUDA version 12.2), your experience may vary on other platforms. 

There are three main components to this repository:
 - Huggingface text-generation-inference: we pass the model name to this service. You can change the model name in the docker-compose file.
 - mongodb: this is the database that stores the conversations for the UI. 
 - chatbot-ui: this is the UI for the chatbot. The UI handles the prompting, you can customize it by changing the configuration in `chat-ui/.env.local`. More information is available in the [huggingface post](https://huggingface.co/blog/llama2#how-to-prompt-llama-2) and [chat-ui issue](https://github.com/huggingface/chat-ui/issues/361).






