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

## Tested Environment
- NVIDIA RTX 3090, Driver 535.86.05, CUDA version 12.2
- 2 x NVIDIA RTX 2080 Ti, Driver 470.182.03 , CUDA version 11.4


## Models
- daryl149/llama-2-7b-chat-hf (unofficial, default)
- meta-llama/Llama-2-7b-chat-hf (needs approval)
- georgesung/llama2_7b_chat_uncensored (supposedly it is less politically correct, not tested)