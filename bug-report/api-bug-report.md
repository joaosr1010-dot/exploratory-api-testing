# Bug Report

## Título

API aceita criação de usuário com payload vazio

## Endpoint

POST /users

## Descrição

Durante os testes exploratórios foi identificado que a API aceita a criação de um usuário mesmo quando o payload enviado está vazio.

## Passos para reproduzir

1. Enviar requisição POST para /users
2. Enviar payload vazio {}

## Resultado esperado

A API deveria retornar erro informando que os campos obrigatórios estão ausentes.

## Resultado obtido

A API retorna status 201 simulando criação do recurso.

## Severidade

Baixa
