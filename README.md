# API REST - Hábitos do Usuário

Criei esta API REST para registrar hábitos de usuários utilizando a arquitetura em camadas, seguindo boas práticas de organização de código e responsabilidade única.

Esta API permite o cadastro de usuários e hábitos, com autenticação JWT e documentação Swagger

A aplicação inclui:

✅ Autenticação de usuários

✅ Execução de testes automatizados

✅ Ambiente de configuração com .env

✅ Cobertura de testes via app, mock e chamadas externas

✅ Simulações com Sinon

✅ Integração com pipeline (CI/CD)

🔧 **Tecnologias e Ferramentas Utilizadas**

Node.js + Express

Arquitetura em camadas (Controller, Service, Model)

Mocha (test runner)

Chai (assertions)

Sinon (mocks)

Supertest (testes de endpoints HTTP)

dotenv (variáveis de ambiente)

**Padrões de teste:**

Testes unitários com mock

Testes de integração com app

Testes de integração externo

Testes externos com chamada via BASE_URL_REST

## Instalação

1. Clone o repositório ou copie os arquivos para seu ambiente.
2. Instale as dependências:
   ```powershell
   npm install express swagger-ui-express jsonwebtoken bcryptjs
   ```

## Execução

- Para iniciar o servidor:
  ```powershell
  node server.js
  ```
- Para importar o app em testes:
  ```js
  const app = require('./app');
  ```

## Endpoints

- `POST /users/register` — Cadastro de usuário (login e senha obrigatórios)
- `POST /users/login` — Login (retorna JWT)
- `GET /users` — Lista todos os usuários
- `POST /habits` — Cadastra hábito (JWT obrigatório)
- `GET /habits` — Lista hábitos do usuário logado (JWT obrigatório)
- `GET /api-docs` — Documentação Swagger

## Autenticação

- Para acessar rotas de hábitos, inclua o token JWT no header:
  ```
  Authorization: Bearer <seu_token>
  ```

## Testes

- O arquivo `app.js` pode ser importado em testes com Supertest.

## Observações

- O banco de dados é em memória, os dados são perdidos ao reiniciar o servidor.
- Não é permitido cadastrar usuários ou hábitos duplicados.
- O Swagger já está configurado e disponível em `/api-docs`.
