# Notas do Teste Exploratório

Durante os testes exploratórios foram realizadas diversas interações com a API para observar seu comportamento em diferentes cenários.

Foram testados cenários positivos e negativos utilizando diferentes tipos de dados e requisições.

Os testes incluíram:

- listagem de usuários
- busca por usuário específico
- busca por usuário inexistente
- criação de usuário
- criação com payload inválido
- atualização de usuário
- exclusão de usuário
- utilização de endpoints inexistentes

---

## Teste 1 – Listar usuários

Endpoint:
GET /users

Resultado esperado:
A API deve retornar a lista de usuários cadastrados com status 200.

Resultado obtido:
Status 200 com retorno da lista de usuários em formato JSON.

Conclusão:
A API responde corretamente à requisição de listagem de usuários.

---

## Teste 2 – Buscar usuário por ID

Endpoint:
GET /users/1

Resultado esperado:
Retornar os dados do usuário correspondente ao ID informado com status 200.

Resultado obtido:
Status 200 com retorno das informações do usuário.

Conclusão:
A API retorna corretamente os dados do usuário solicitado.

---

## Teste 3 – Buscar usuário inexistente

Endpoint:
GET /users/9999

Resultado esperado:
A API deve retornar status 404 indicando que o recurso não foi encontrado.

Resultado obtido:
Status 404 Not Found.

Conclusão:
A API retorna corretamente o status informando que o usuário solicitado não existe.

---

## Teste 4 – Criar usuário com payload válido

Endpoint:
POST /users

Payload enviado:

{
"name": "João",
"email": "joao@email.com"
}

Resultado esperado:
A API deve aceitar a criação do usuário e retornar status 201.

Resultado obtido:
Status 201 simulando a criação do usuário.

Conclusão:
A API aceita corretamente a requisição de criação de usuário.

---

## Teste 5 – Criar usuário com payload vazio

Endpoint:
POST /users

Payload enviado:

{}

Resultado esperado:
A API deveria validar os campos obrigatórios e retornar erro.

Resultado obtido:
A API retorna status 201 simulando criação do recurso.

Observação:
A API aceita payload vazio. Em uma API real isso poderia indicar falha de validação.

---

## Teste 6 – Atualizar usuário

Endpoint:
PUT /users/1

Payload enviado:

{
"name": "João QA"
}

Resultado esperado:
A API deve aceitar a atualização do usuário e retornar status 200 ou 204.

Resultado obtido:
Status 200 simulando atualização do recurso.

Conclusão:
A API aceita corretamente a requisição de atualização de usuário.

---

## Teste 7 – Excluir usuário

Endpoint:
DELETE /users/1

Resultado esperado:
A API deve aceitar a exclusão do usuário e retornar status 200 ou 204.

Resultado obtido:
Status 200 simulando exclusão do recurso.

Conclusão:
A API aceita corretamente a requisição de exclusão do usuário.

---

## Teste 8 – Endpoint inexistente

Endpoint:
GET /userss

Resultado esperado:
A API deve retornar erro informando que o endpoint não existe.

Resultado obtido:
Status 404 Not Found.

Conclusão:
A API responde corretamente para endpoint inexistente.
