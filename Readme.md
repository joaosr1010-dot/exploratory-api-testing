# Exploratory API Testing – JSONPlaceholder

Este projeto foi desenvolvido como parte dos meus estudos em Quality Assurance (QA) com o objetivo de praticar **testes exploratórios em APIs REST**.

Os testes foram executados utilizando o Postman na API pública JSONPlaceholder, explorando diferentes cenários positivos e negativos para observar o comportamento das respostas da API.

---

# 🎯 Objetivo

Praticar:

- Testes exploratórios em APIs
- Execução de requisições HTTP
- Validação de respostas da API
- Testes positivos e negativos
- Documentação de testes

---

# 🛠 Ferramentas utilizadas

- Postman
- GitHub

---

# 🌐 API utilizada

https://jsonplaceholder.typicode.com

---

# 🔎 Endpoints testados

## Listar usuários

GET /users

Status esperado  
200 OK

Descrição  
Retorna a lista de usuários cadastrados.

---

## Buscar usuário por ID

GET /users/1

Status esperado  
200 OK

Descrição  
Retorna os dados do usuário correspondente ao ID informado.

---

## Buscar usuário inexistente

GET /users/9999

Status esperado  
404 Not Found

Descrição  
Valida o comportamento da API ao solicitar um usuário que não existe.

---

## Criar usuário

POST /users

Payload utilizado

{

"name": "João",

"email": "joao@email.com"

}

Status esperado  
201 Created

Descrição  
Simula a criação de um novo usuário.

---

## Criar usuário com payload vazio

POST /users

Payload utilizado

{}

Resultado observado  
201 Created

Observação  
A API aceita payload vazio e simula a criação do recurso.  
Em uma API real seria esperado erro de validação para campos obrigatórios.

---

## Criar usuário com tipo de dado inválido

POST /users

Payload utilizado

{

"name": 12345

}

Resultado observado  
201 Created

Observação  
A API aceita o payload mesmo com tipo de dado inválido.  
Isso ocorre porque a JSONPlaceholder é uma API de testes e não realiza validação real de dados.

---

## Criar usuário com campos extras

POST /users

Payload utilizado

{

"name": "João",

"age": 999,

"admin": true

}

Resultado observado  
201 Created

Observação  
A API aceita campos adicionais no payload e simula a criação do usuário.  
Em uma API real seria esperado que campos inesperados fossem ignorados ou retornassem erro de validação.

---

## Atualizar usuário

PUT /users/1

Payload utilizado

{

"name": "João QA"

}

Status esperado  
200 OK

Descrição  
Simula a atualização de um usuário existente.

---

## Excluir usuário

DELETE /users/1

Status esperado  
200 OK ou 204 No Content

Descrição  
Simula a exclusão de um usuário.

---

## ID inválido

GET /users/abc

Resultado observado  
404 Not Found

Descrição  
Teste para verificar o comportamento da API ao receber um ID inválido.

---

## Endpoint inexistente

GET /userss

Resultado observado  
404 Not Found

Descrição  
Teste para verificar o comportamento da API ao acessar um endpoint inexistente.

---

# 📂 Estrutura do projeto

README.md → descrição do projeto  
exploratory-test-charter → planejamento do teste exploratório  
test-notes → registro dos testes executados  
bug-report → exemplo de bug report  
postman-collection → coleção utilizada no Postman  
evidences → capturas de tela da execução dos testes

---

# 🧪 Tipos de testes realizados

Durante a execução deste projeto foram aplicados diferentes tipos de testes para explorar o comportamento da API:

- Testes positivos → validação de requisições válidas e funcionamento esperado dos endpoints
- Testes negativos → envio de dados inválidos ou requisições incorretas para observar como a API responde
- Testes exploratórios → exploração do comportamento da API em diferentes cenários sem roteiro rígido

Os testes foram executados utilizando o Postman na API pública JSONPlaceholder.

---

# 📚 Aprendizados

Durante este projeto foi possível praticar:

- Testes exploratórios em APIs
- Utilização do Postman
- Análise de respostas HTTP
- Execução de cenários positivos e negativos
- Documentação de testes
- Registro de possíveis inconsistências no comportamento da API

---

# 👨‍💻 Autor

Projeto desenvolvido como parte dos meus estudos para atuar como **QA Jr (Quality Assurance)**.
