docker run -it --pull=always --rm -v "C:\\Users\\User\\ollama:/root/.ollama" -p 11434:11434 -e OLLAMA_KEEP_ALIVE="-1" --name "ollama" --rm --gpus all ollama/ollama:latest

docker exec -it ollama wget -P /root/.ollama https://raw.githubusercontent.com/coffeegrind123/docker-ollama/main/noromaid.Modelfile

docker exec -it ollama wget -P /root/.ollama/models https://huggingface.co/NeverSleep/Noromaid-v0.4-Mixtral-Instruct-8x7b-Zloss-GGUF/resolve/main/Noromaid-v0.4-Mixtral-Instruct-8x7b.q4_k_m.gguf

docker exec -it ollama ollama create noromaid -f /root/.ollama/noromaid.Modelfile

docker exec -it ollama ollama run noromaid

#docker exec -it ollama ollama show --modelfile dolphin-mixtral:8x7b

#docker exec -it ollama ollama list
