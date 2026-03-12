# Exploratory Test Charter

## Objetivo
Explorar o comportamento da API ReqRes identificando possíveis falhas, respostas inesperadas ou inconsistências.

## Área explorada
Endpoints relacionados a usuários.

## Endpoints testados

GET /users
GET /users/{id}
POST /users
PUT /users/{id}
DELETE /users/{id}

## Estratégia

Durante os testes foram realizadas explorações como:

- envio de IDs inexistentes
- envio de payloads inválidos
- ausência de campos obrigatórios
- alteração de tipos de dados
- envio de payload vazio
