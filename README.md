# SketchRNN HTTP Web Server Service

Autocomplete sketches provided a model name & a list of drawn points via SketchRNN. It'll automatically draw sketches relative to the input data (i.e. no coordinate transformations required). Modified from the original example at https://github.com/MindExMachina/smartgeometry.

### Input data format
- Model name
  - Available models to choose from are listed here: https://github.com/tobyloki/SketchRNNHttpServer/tree/master/services/sketch-rnn/lib/models
- List of points:
  - Each point contains:
    - (x, y) coordinate
    - (pen down, pen up, pen done) 1 hot encoding
    - Format: (x, y, up, down, done)
      - e.g. (20.0, 30.4, 1, 0, 0)

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
