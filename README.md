# SketchRNN HTTP Web Server Service
## Run from inside Docker container
```bash
docker run -it -d -p 80:80 --name sketchrnn-http-server node:latest

docker exec -it sketchrnn-http-server /bin/sh

bash

cd

apt-get update -y

npm i -g pnpm
```

## Setup Instructions
```bash
git clone https://github.com/tobyloki/SketchRNNHttpServer.git

cd SketchRNNHttpServer/services/sketch-rnn

pnpm i

node http-server.js
```
Test sample endpoint GET http://localhost:80/simple_predict

## Host publicly via ngrok
1. Follow instructions to set up ngrok: https://ngrok.com/download
2. Run ngrok
```bash
ngrok http 80
```
3. Copy forwarding endpoint (e.g. https://\<id\>.ngrok-free.app)
