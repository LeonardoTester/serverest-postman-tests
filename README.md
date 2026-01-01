# serverest-postman-tests
Testes automatizados da API ServeRest com Postman

API ServeRest com Postman![Postman Collection](https://img.shields.io/badge/Postman-Coleção-orange?style=for-the-badge&logo=postman)
![ServeRest API](https://img.shields.io/badge/API-ServeRest-blue?style=for-the-badge)Coleção Postman com testes automatizados para a API ServeRest (https://serverest.dev) — uma API REST de e-commerce simulada perfeita para praticar testes de API.A coleção inclui fluxos dinâmicos: cadastro de usuário, login, criação de produto, busca por ID, edição, exclusão e operações de carrinho. Tudo usando variáveis, scripts de pré-request e asserções para rodar 100% automatizado no Collection Runner.FuncionalidadesDados dinâmicos: nomes de usuários/produtos aleatórios e IDs salvos automaticamente em variáveis globais.
Autenticação: extrai o token Bearer do login e usa em endpoints protegidos.
Testes automatizados: verificação de status code, tempo de resposta, mensagens, etc.
Encadeamento de requests: Cria → Busca por ID → Exclui (sempre limpa depois).
Cobertura de endpoints: /login, /usuarios, /produtos, /carrinhos.

Arquivos do RepositórioCollection - ServeRest.postman_collection.json → Coleção principal com todas as requests, scripts e testes.
Serverest Dev.postman_environment.json → Variáveis de ambiente (defina baseURL como https://serverest.dev).
workspace.postman_globals.json → Variáveis globais (token, IDs dinâmicos, dados aleatórios).

Como UsarClone ou baixe este repositório.
Abra o Postman:Vá em File → Import.
Selecione os três arquivos JSON.
Ordem de importação: Globals → Environment → Collection.

No environment Serverest Dev:Defina o valor de baseURL como https://serverest.dev (se ainda não estiver preenchido).

Selecione a coleção Collection - ServeRest.
Execute com Collection Runner:Escolha o environment "Serverest Dev".
Clique em Run → Todos os testes devem passar em verde! 

Dicas para Execução PerfeitaRode as pastas na ordem: Login → Usuários (cadastro opcional) → Produtos (criar → buscar → excluir).
O fluxo principal de produtos é totalmente independente e limpa os dados criados.
Caso queira testar cadastro de usuário, rode a pasta Usuários primeiro.

