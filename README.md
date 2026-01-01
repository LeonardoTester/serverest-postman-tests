# 📦 ServeRest – API Testing Collection (Postman)

Este projeto contém uma coleção do Postman criada para testar a API pública **ServeRest**  
🔗 [https://serverest.dev](https://serverest.dev)

O foco está em **testes automatizados de API**, validação de contrato, regras de negócio e performance, demonstrando minhas habilidades como **QA Engineer**.

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

**Script de extração (aba Tests do Login):**

```javascript

let responseJson = pm.response.json();
let tokenSplit = responseJson.authorization.split(' ');
pm.environment.set("AcessToken", tokenSplit[1]); 


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

javascript:
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Registro excluído com sucesso", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.message).to.eql("Registro excluído com sucesso");
});
