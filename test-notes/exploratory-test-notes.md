# Exploratory Test Notes

Durante os testes exploratórios foram realizadas diversas interações com os endpoints da API para observar comportamentos esperados e inesperados.

## Teste 1 - Buscar usuários

Endpoint:
GET /users

Resultado:
API retornou lista de usuários com status 200.

Observação:
Resposta estruturada corretamente em JSON.

---

## Teste 2 - Buscar usuário inexistente

Endpoint:
GET /users/999

Resultado esperado:
404 Not Found

Resultado obtido:
404 Not Found

---

## Teste 3 - Criar usuário com payload válido

Endpoint:
POST /users

Payload:

{
"name": "João",
"job": "QA Tester"
}

Resultado:
Usuário criado com status 201.

---

## Teste 4 - Criar usuário com payload vazio

Endpoint:
POST /users

Payload:

{}

Resultado observado:
API aceitou a requisição e retornou status 201.

Observação:
Comportamento inesperado.
