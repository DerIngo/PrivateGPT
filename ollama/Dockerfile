# Use the specified Python base image
FROM python:3.11-slim

# Set the working directory in the container
WORKDIR /app

# Install necessary packages
RUN apt-get update && apt-get install -y \
    git \
    build-essential

# Clone the private repository
RUN git clone https://github.com/imartinez/privateGPT

WORKDIR /app/privateGPT

# Install poetry
RUN pip install poetry

# Lock and install dependencies using poetry
RUN poetry lock
RUN poetry install --extras "ui llms-ollama embeddings-ollama vector-stores-qdrant"

# 
RUN sed -i 's@llm_model: mistral@llm_model: ${OLLAMA_LLM_MODEL:mistral}@g' settings-ollama.yaml
RUN sed -i 's@api_base: http://localhost:11434@api_base: ${OLLAMA_API_BASE:http\://172.17.0.1\:11434}@g' settings-ollama.yaml