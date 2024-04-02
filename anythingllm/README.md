# AnythingLLM with Ollama
Well, obviously <a href="https://github.com/Mintplex-Labs/anything-llm">AnythingLLM</a> is not PrivateGPT.<br/>
But after getting PrivateGPT running, it was so easy to start AnythingLLM and so less to document, I decided to add the knowledge ("one docker command") to this project.

## Ollama
Install Ollama from <a href="https://ollama.com/">https://ollama.com/</a><br/>
Start Ollama:

```
export OLLAMA_HOST=0.0.0.0:11434
ollama serve
```

## Start AnythingLLM
```
export STORAGE_LOCATION=$HOME/anythingllm && \
mkdir -p $STORAGE_LOCATION && \
touch "$STORAGE_LOCATION/.env" && \
docker run -d -p 3001:3001 \
--cap-add SYS_ADMIN \
--add-host=host.docker.internal:host-gateway \
--name anythingllm \
-v ${STORAGE_LOCATION}:/app/server/storage \
-v ${STORAGE_LOCATION}/.env:/app/server/.env \
-e STORAGE_DIR="/app/server/storage" \
mintplexlabs/anythingllm

# watch logs:
docker logs --follow anythingllm
```
## Use AnythingLLM
AnythingLLM will be exposed at: <a href="http://localhost:3001">http://localhost:3001</a>