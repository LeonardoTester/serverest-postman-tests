# 📦 ServeRest – API Testing Collection (Postman)

Este projeto contém uma coleção do Postman criada para testar a API pública **ServeRest**  
🔗 [https://serverest.dev](https://serverest.dev)

O foco está em **testes automatizados de API**, validação de contrato, regras de negócio e performance, demonstrando minhas habilidades como **QA Engineer**.

[![Postman](https://img.shields.io/badge/Postman-Coleção-orange?style=for-the-badge&logo=postman)](https://www.postman.com/)
[![ServeRest API](https://img.shields.io/badge/API-ServeRest-blue?style=for-the-badge)](https://serverest.dev/)

## 🎯 Objetivo

Aplicar testes automatizados em uma API REST para validar:

- Estrutura dos dados (JSON)
- Tipos de dados (string, number, array)
- Regras de negócio
- Status Code corretos
- Mensagens de retorno
- Performance da API
- Autenticação via Token
- Uso de variáveis e ambientes

## 🌐 Base URL

A API base é configurada no Environment do Postman:

| Variável  | Valor                   |
|-----------|-------------------------|
| baseURL   | https://serverest.dev   |

## 🔐 Autenticação

Após o login, o token é automaticamente extraído e armazenado na variável de ambiente **AcessToken**.  
Ele é usado nos endpoints protegidos (criar produto, editar/excluir usuário, etc.).


## 📁 Estrutura da Collection
ServeRest/
├── Login
│   └── POST Login
│
├── Usuários
│   ├── GET Listar todos
│   ├── POST Cadastrar usuário (com dados aleatórios)
│   ├── GET Buscar por ID
│   ├── PUT Editar usuário
│   └── DELETE Deletar usuário
│
├── Produtos
│   ├── GET Listar produtos
│   ├── POST Cadastrar produto (com nome aleatório)
│   ├── GET Buscar produto por ID (usa ID dinâmico)
│   ├── PUT Editar produto
│   └── DELETE Deletar produto (com verificação de mensagem)
│
└── Carrinhos
    ├── GET Listar carrinhos
    ├── POST Cadastrar carrinho
    ├── GET Buscar carrinho por ID
    ├── DELETE Concluir compra
    └── DELETE Cancelar compra

## ⚙️ Variáveis Utilizadas

### Environment

| Variável     | Descrição                     |
|--------------|-------------------------------|
| baseURL      | URL base da API               |
| AcessToken   | Token Bearer após login       |

### Globais

| Variável         | Descrição                                          |
|------------------|----------------------------------------------------|
| email / nome     | Gerados aleatoriamente no cadastro de usuário      |
| password         | Senha fixa ou dinâmica                             |
| RandomProduct    | Nome aleatório do produto                          |
| NewProductID     | ID do produto criado (salvo automaticamente)       |

## ✅ Testes Automatizados Implementados

Todos os endpoints principais possuem testes para:

- Status Code esperado
- Estrutura e tipos do corpo da resposta (JSON)
- Validação de mensagens de sucesso/erro
- Content-Type correto
- Tempo de resposta (< 200ms em alguns casos)
- Validação condicional (ex: salva ID apenas se 201)
- Limpeza de dados (delete após create)

**Exemplo no DELETE de produto:**


## 🚀 Como Executar a Collection

1. Abra o **Postman**
2. Clique em **Import**
3. Importe os arquivos do repositório:
   - `Collection - ServeRest.postman_collection.json`
   - `Serverest Dev.postman_environment.json`
   - `workspace.postman_globals.json`
4. Selecione o environment **Serverest Dev**
5. Defina `baseURL` como `https://serverest.dev` (se necessário)
6. Execute via **Collection Runner** → Todos os testes devem passar em verde! 🎉

## 💻 Tecnologias Utilizadas

- Postman
- JavaScript (scripts Pre-request e Tests)
- API REST
- JSON

## 🧠 Competências Demonstradas

- Testes de API
- Automação com Postman
- Validação de contrato e regras de negócio
- Manipulação dinâmica de dados e variáveis
- Encadeamento de requests (fluxos automatizados)
- Boas práticas de QA e limpeza de dados

