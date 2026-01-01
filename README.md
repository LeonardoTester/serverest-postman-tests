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
