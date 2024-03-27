# PrivateGPT with Ollama
## Ollama
Install Ollama from <a href="https://ollama.com/">https://ollama.com/</a><br/>
Start Ollama:
```
export OLLAMA_HOST=0.0.0.0:11434
ollama serve
```

## Build PrivateGPT Image
```
docker build -t privategptollama .
```
## Start PrivateGPT
```
export DOCKER_GATEWAY_HOST="`/sbin/ip route|awk '/dev eth0 proto kernel/{print $9}'|xargs`"
docker-compose up -d

# watch logs:
docker logs --follow privategptollama
```
## Use PrivateGPT
PrivateGPT will be exposed at: <a href="http://localhost:8001">http://localhost:8001</a>