# Testes Automatizados da API ServeRest com Postman

[![Postman](https://img.shields.io/badge/Postman-Coleção-orange?style=for-the-badge&logo=postman)](https://www.postman.com/)
[![ServeRest API](https://img.shields.io/badge/API-ServeRest-blue?style=for-the-badge)](https://serverest.dev/)

Coleção Postman com **testes automatizados** para a API **ServeRest** ([https://serverest.dev](https://serverest.dev)) — uma API REST de e-commerce simulada, perfeita para praticar testes de API.

A coleção inclui fluxos dinâmicos como cadastro de usuário, login, criação de produto, busca por ID, edição, exclusão e operações de carrinho. Tudo utilizando variáveis, scripts de pré-request e asserções para rodar 100% automatizado no **Collection Runner**.

## Funcionalidades

- **Dados dinâmicos**: nomes aleatórios para usuários e produtos, IDs salvos automaticamente em variáveis globais.
- **Autenticação**: extrai o token Bearer do login e reutiliza em endpoints protegidos.
- **Asserções automáticas**: verifica status code, tempo de resposta, mensagens, etc.
- **Encadeamento de requests**: Cria → Busca por ID → Exclui (sempre limpa os dados criados).
- Cobertura de endpoints: `/login`, `/usuarios`, `/produtos`, `/carrinhos`.

## Arquivos do Repositório

- `Collection - ServeRest.postman_collection.json` → Coleção principal com todas as requests, scripts e testes.
- `Serverest Dev.postman_environment.json` → Variáveis de ambiente (defina `baseURL` como `https://serverest.dev`).
- `workspace.postman_globals.json` → Variáveis globais (token, IDs dinâmicos, dados aleatórios).

## Como Usar

1. Clone ou baixe este repositório.
2. Abra o **Postman**:
   - Vá em **File → Import**.
   - Selecione os três arquivos JSON.
   - **Ordem recomendada**: Globals → Environment → Collection.
3. No environment **Serverest Dev**, defina:
   - `baseURL` → `https://serverest.dev`
4. Selecione a coleção **Collection - ServeRest**.
5. Execute com **Collection Runner**:
   - Escolha o environment "Serverest Dev".
   - Clique em **Run** → Todos os testes devem passar em verde! 🎉

## Dicas para Execução Perfeita

- Rode as pastas na ordem sugerida: **Login** → **Usuários** (opcional) → **Produtos** (criar → buscar → excluir).
- O fluxo de **Produtos** é totalmente independente e limpa os dados ao final.
- Para testar cadastro de usuário dinâmico, execute a pasta **Usuários** primeiro.
