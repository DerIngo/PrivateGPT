# PrivateGPT with ChatGPT
## OpenAI API key
You need an OpenAI API key from <a href="https://platform.openai.com/api-keys">OpenAI</a><br/>
The key itself is free, but I needed to charge my account with 5$ to get it working..<br/>
You have to copy file <i>.env.example</i> to <i>.env</>> and enter your OpenAI API key in file <i>.env</i>.

## Build PrivateGPT Image
```
docker build -t privategptopenai .
```
## Start PrivateGPT
```
docker-compose up -d

# watch logs:
docker logs --follow privategpt
```
## Use PrivateGPT
PrivateGPT will be exposed at: <a href="http://localhost:8001">http://localhost:8001</a>