# Local Llama-2 

## Intorduction

This repository contains docker-compose file for running Llama-2 locally. I have tested this on Linux using NVIDIA GPUs (Driver 535.86.05, CUDA version 12.2), your experience may vary on other platforms. 

There are three main components to this repository:
 - Huggingface text-generation-inference: we pass the model name to this service. You can change the model name in the docker-compose file.
 - mongodb: this is the database that stores the conversations for the UI. 
 - chatbot-ui: this is the UI for the chatbot. The UI handles the prompting, you can customize it by changing the configuration in `chat-ui/.env.local`. More information is available in the [huggingface post](https://huggingface.co/blog/llama2#how-to-prompt-llama-2) and [chat-ui issue](https://github.com/huggingface/chat-ui/issues/361).

## Requirements
- [docker desktop](https://docs.docker.com/desktop/install/ubuntu/)
- [NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html)
- NVIDIA GPUs 

## Usage

In order to run the chat model locally, you only need to run the following command. Note that the first time you run this command, it will download the docker images for the services. This may take a while depending on your internet connection.

```
cd local-llm 

docker compose up huggingface_inference # takes a while to download the model
docker compose up mongo_chatui
docker compose up chat_ui


# Later runs can be done with the following command! 
docker compose up
```


## Tested Environment
- NVIDIA RTX 3090, Driver 535.86.05, CUDA version 12.2
- 2 x NVIDIA RTX 3090 Ti, Driver 525.125.06  , CUDA version 12.0

## Models
- daryl149/llama-2-7b-chat-hf (unofficial, default)
- meta-llama/Llama-2-7b-chat-hf (needs approval)
- georgesung/llama2_7b_chat_uncensored (supposedly it is less politically correct, not tested)



