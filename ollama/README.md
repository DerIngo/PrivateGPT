# PrivateGPT with Ollama
## OpenAI API key
You need an OpenAI API key from <a href="https://platform.openai.com/api-keys">OpenAI</a><br/>
The key itself is free, but I needed to charge my account with 5$ to get it working..<br/>
You have to copy file <i>.env.example</i> to <i>.env</>> and enter your OpenAI API key in file <i>.env</i>.

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