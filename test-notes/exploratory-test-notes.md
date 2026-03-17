# 🧪 Notas do Teste Exploratório

## 🎯 Objetivo

Realizar testes exploratórios na API JSONPlaceholder com o objetivo de identificar comportamentos inesperados, falhas de validação e inconsistências nas respostas.

---

## 🔎 Abordagem de Teste Exploratório

Os testes foram realizados de forma exploratória, sem roteiros rígidos, permitindo maior liberdade na investigação do comportamento da API.

Durante a execução, foram utilizadas diferentes variações de entrada, incluindo:

* Dados válidos e inválidos
* Payloads vazios ou incompletos
* Tipos de dados incorretos
* Endpoints inexistentes
* IDs inválidos e inexistentes

A exploração foi conduzida com foco em identificar falhas de validação e analisar a consistência das respostas retornadas pela API.

---

## 🧪 Testes Executados

### 🧪 Teste 1 – Listar usuários

**Endpoint:** GET /users

**Resultado esperado:**
A API deve retornar a lista de usuários com status 200.

**Resultado obtido:**
Status 200 com retorno da lista de usuários em formato JSON.

**Observações:**
A API responde corretamente à requisição de listagem.

---

### 🧪 Teste 2 – Buscar usuário por ID

**Endpoint:** GET /users/1

**Resultado esperado:**
Retornar os dados do usuário correspondente ao ID informado com status 200.

**Resultado obtido:**
Status 200 com retorno das informações do usuário.

**Observações:**
A API retorna corretamente os dados do usuário solicitado.

---

### 🧪 Teste 3 – Buscar usuário inexistente

**Endpoint:** GET /users/9999

**Resultado esperado:**
A API deve retornar status 404 indicando que o recurso não foi encontrado.

**Resultado obtido:**
Status 404 Not Found.

**Observações:**
A API trata corretamente requisições para recursos inexistentes.

---

### 🧪 Teste 4 – Criar usuário com payload válido

**Endpoint:** POST /users

**Payload enviado:**

```json
{
  "name": "João",
  "email": "joao@email.com"
}
```

**Resultado esperado:**
A API deve aceitar a criação do usuário e retornar status 201.

**Resultado obtido:**
Status 201 simulando a criação do usuário.

**Observações:**
A API aceita corretamente requisições válidas de criação.

---

### 🧪 Teste 5 – Criar usuário com payload vazio

**Endpoint:** POST /users

**Payload enviado:**

```json
{}
```

**Resultado esperado:**
A API deveria validar os campos obrigatórios e retornar erro.

**Resultado obtido:**
A API retorna status 201 simulando criação do recurso.

**Observações:**
A API aceita payload vazio. Em um cenário real, isso indicaria ausência de validação de campos obrigatórios.

---

### 🧪 Teste 6 – Criar usuário com tipo de dado inválido

**Endpoint:** POST /users

**Payload enviado:**

```json
{
  "name": 12345
}
```

**Resultado esperado:**
A API deveria validar o tipo de dado e retornar erro.

**Resultado obtido:**
A API retorna status 201 simulando criação do recurso.

**Observações:**
A API não valida o tipo de dado enviado, permitindo dados inconsistentes.

---

### 🧪 Teste 7 – Criar usuário com campos extras

**Endpoint:** POST /users

**Payload enviado:**

```json
{
  "name": "João",
  "age": 999,
  "admin": true
}
```

**Resultado esperado:**
A API deveria ignorar ou validar campos não previstos.

**Resultado obtido:**
A API aceita os campos extras sem validação.

**Observações:**
A API não possui validação de schema, aceitando propriedades não definidas.

---

### 🧪 Teste 8 – Atualizar usuário

**Endpoint:** PUT /users/1

**Payload enviado:**

```json
{
  "name": "João QA"
}
```

**Resultado esperado:**
A API deve aceitar a atualização e retornar status 200 ou 204.

**Resultado obtido:**
Status 200 simulando atualização do recurso.

**Observações:**
A API aceita corretamente a atualização.

---

### 🧪 Teste 9 – Excluir usuário

**Endpoint:** DELETE /users/1

**Resultado esperado:**
A API deve aceitar a exclusão e retornar status 200 ou 204.

**Resultado obtido:**
Status 200 simulando exclusão do recurso.

**Observações:**
A API responde corretamente à exclusão.

---

### 🧪 Teste 10 – ID inválido

**Endpoint:** GET /users/abc

**Resultado esperado:**
A API deveria validar o formato do ID e retornar erro apropriado (ex: 400 Bad Request).

**Resultado obtido:**
Status 404 Not Found.

**Observações:**
A API não diferencia ID inválido de recurso inexistente, o que pode dificultar o tratamento de erros.

---

### 🧪 Teste 11 – Endpoint inexistente

**Endpoint:** GET /userss

**Resultado esperado:**
A API deve retornar erro informando que o endpoint não existe.

**Resultado obtido:**
Status 404 Not Found.

**Observações:**
A API responde corretamente para endpoints inválidos.

---

## 📊 Resumo da Exploração

Durante os testes exploratórios, foi possível identificar que a API apresenta comportamento consistente em cenários básicos, como listagem, busca e manipulação de usuários.

Por outro lado, foram observadas limitações importantes relacionadas à validação de dados, como:

* Aceitação de payloads vazios
* Falta de validação de tipos de dados
* Aceitação de campos não previstos
* Tratamento genérico para IDs inválidos

Esses comportamentos indicam que a API possui caráter demonstrativo e não implementa validações robustas, o que seria essencial em um ambiente produtivo.

A abordagem exploratória permitiu identificar cenários que não seriam cobertos apenas com testes funcionais tradicionais, aumentando significativamente a cobertura e a qualidade da análise.
