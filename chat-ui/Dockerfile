FROM node:19



RUN apt update && apt install git
RUN mkdir /app 

WORKDIR /app
RUN git clone https://github.com/huggingface/chat-ui.git

WORKDIR /app/chat-ui


RUN npm install
