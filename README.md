# SketchRNN HTTP Web Server Service
## Run from inside Docker container
```bash
docker run -it -d -p 80:80 --name sketchrnn-http-server node:latest

docker exec -it {containerId} /bin/sh

apt-get update -y

npm i -g pnpm
```

## Instructions
```bash
git clone https://github.com/tobyloki/SketchRNNHttpServer.git

cd services/sketch-rnn

pnpm i

node http-server.js
```
Test sample endpoint GET http://localhost:80/simple_predict
