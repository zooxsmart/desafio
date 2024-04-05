# Desafio Front Zoox

## Observações técnicas importantes:
- Desenvolver utilizando VueJS;
- Pode ser utilizada a biblioteca visual de sua escolha;
- A solução deve ser publicada no github e deve conter um readme com instruções
para execução.

## Critérios de avaliação:
1. Manutenibilidade;
2. Simplicidade;
3. Testabilidade;
4. Responsividade.

## Bônus:
- Fácil execução é um ponto favorável;
- Uma boa documentação facilita muito.

Se tiver qualquer dúvida é só perguntar, ligar, entrar em contato.
Estaremos à disposição.

## Desafio

A ideia do desafio é criar um cenário semelhante ao que você vai vivenciar no dia a dia.

Nesse projeto, você terá que implementar uma busca de dados demográficos de cidades por CEP.

**Caso de uso:** Como usuário, gostaria de consultar os dados demográficos do Rio de Janeiro e visualizar isso de maneira fácil plotado no mapa.

**Layout:** Figma [Link Figma](https://www.figma.com/proto/zctZGUaeEcJ7CGXuQKrC6a/teste-front?type=design&node-id=1-6935&t=lSBdvA69Yadb6uqg-1&scaling=min-zoom&page-id=0%3A1&starting-point-node-id=1%3A3232&show-proto-sidebar=1&mode=design). Seguir as especificações lá feitas.

### Rodando a aplicação

Entendemos que para essa vaga seja importante um pouco de conhecimento de como rodar aplicações.
Para conseguir fazer as rodar a API, disponibilizamos o seguinte docker-compose rodar a API, já configurado com os endpoints e dados.

```yaml
version: "3.9"

services:
  api:
    container_name: api
    hostname: api
    build: zooxsmart/desafio-api:latest
    ports:
      - 3333:3333
    networks:
      - api-network
    depends_on:
      db:
        condition: service_healthy
    extra_hosts:
      - "host.docker.internal:host-gateway"

  db:
    container_name: db
    hostname: db
    image: zooxsmart/postgres-desafio:latest
    restart: always
    ports:
      - "5432:5432"
    networks:
      - api-network
    volumes:
      - api-data:/var/lib/postgresql/data
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U api"]
      interval: 1s
      timeout: 1s
      retries: 15

networks:
  api-network:
    driver: bridge

volumes:
  api-data:
``` 

### Endpoints para serem utilizados no projeto:

Para o desafio, disponibilizamos dados referentes às cidades dos estados de SP e RJ.

#### Busca dos CEPs

```
curl --location 'http://localhost:3333/geo?search=0000'
```

#### Busca dos polígonos para o mapa

```
curl --location 'http://localhost:3333/geo/:state_id/:city_id/demographic'
```

#### Busca dos dados demográficos

```
curl --location 'http://localhost:3333/geo/:state_id/:city_id/demographic'
```