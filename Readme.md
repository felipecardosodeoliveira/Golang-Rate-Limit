# Golang Rate Limiter

Este projeto é uma implementação de um limitador de taxa em Go, utilizando Redis como armazenamento. O limitador permite limitar requisições por IP e por token.


## Instalação

1. **Clone o repositório**:
   ```bash
   git clone https://github.com/seu_usuario/golang-rate-limit.git
   cd Golang-Rate-Limit/ 

2. **Váriaveis de ambiente**
   RATE_LIMIT_IP=1 (limite por ip)
   RATE_LIMIT_TOKEN=2 (limite por token)
   BLOCK_TIME=5   (tempo de bloqueio quando o limite for atingide)
   REDIS_HOST=redis (redis)
   REDIS_PORT=6379  (porta)

3. **Build o projeto**:
   ```bash
      docker compose up --build

4. **Fazendo chamadas http**:

Dentro da pasta doc há um arquivo que pose ser executado para fazer as chamadas por ip ou com o
toke no header.

5. **Testes**:
   ```bash
   Teste com curl
   Para testar o limite de IP:
 
   Copiar código
   ```bash
   for i in {1..5}; do curl -i http://localhost:8080/; done


   Para testar com um token:
   Copiar código
   for i in {1..5}; do curl -i -H "API_KEY: teste_123" http://localhost:8080/; done  

   Para testar com o Apache Bench:
   ```bash
   Copiar código
   ab -n 10 -c 1 http://localhost:8080/


