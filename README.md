<h1 align="center">GYM PASS API 🏋️</h1>

A API foi desenvolvida com o propósito de simplificar o processo de check-in em academias, inspirando-se no bem-sucedido modelo do GYMPASS. Os usuários têm a opção de se registrar como MEMBER ou ADMIN, utilizando autenticação JWT e implementando estratégias de refresh token, juntamente com o controle de acesso baseado em funções (RBAC).

Os usuários com perfil MEMBER têm a capacidade de realizar diversas ações na plataforma, como buscar academias próximas em até (10KM), efetuar buscas pelo nome, realizar check-in em uma academia específica, além de acessar o histórico completo de seus logins. 

Usuários com perfil ADMIN possuem a capacidade de criar academias na plataforma, validar usuários e realizar verificações específicas de usuários com base em horas e datas.

API Também  foi desenvolvida utilizando os princípios do design pattern SOLID, incorporando o repository pattern e implementando uma cobertura abrangente de testes, juntamente com estratégias para um banco de dados in-memory.

## Tecnologias

- [Node](https://nodejs.org/en/docs)
- [Typescript](https://www.typescriptlang.org/docs/)
- [Fastify](https://fastify.dev/docs/latest/)
- [JWT](https://jwt.io/introduction)
- [Docker](https://docs.docker.com/)
- [Zod](https://www.npmjs.com/package/zod)
- [Vitest](https://vitest.dev/)
- [Prisma](https://www.prisma.io/docs/getting-started)

## Instalação

```bash
# Faça o clone do repo
  git clone git@github.com:matheusgmello/gympass-solid-api

# Configure as variáveis de ambiente
  copie do env example

# Rode a imagem do docker
  Docker compose start

# Instale as dependências
  npm install

# Execute o projeto
  npm run start:dev
  
# Rodar as migrations 
  npm run knex -- migrate:latest
```
## Insomnia do projeto
[![Run in Insomnia}](https://insomnia.rest/images/run.svg)](https://insomnia.rest/run/?label=GymSolid-API&uri=https%3A%2F%2Fraw.githubusercontent.com%2Fmatheusgmello%2Fgympass-solid-api%2Fmain%2FExport.json)

## Regras da aplicação 

### RFs (Requisitos funcionais)

- [x] Deve ser possível se cadastrar;
- [x] Deve ser possível se autenticar;
- [x] Deve ser possível obter o perfil de um usuário logado;
- [x] Deve ser possível obter o número de check-ins realizados pelo usuário logado;
- [x] Deve ser possível o usuário obter o seu histórico de check-ins;
- [x] Deve ser possível o usuário buscar academias próximas (até 10km);
- [x] Deve ser possível o usuário buscar academias pelo nome;
- [x] Deve ser possível o usuário realizar check-in em uma academia;
- [x] Deve ser possível validar o check-in de um usuário;
- [x] Deve ser possível cadastrar uma academia;

### RNs (Regras de negócio)

- [x] O usuário não deve poder se cadastrar com um e-mail duplicado;
- [x] O usuário não pode fazer 2 check-ins no mesmo dia;
- [x] O usuário não pode fazer check-in se não estiver perto (100m) da academia;
- [x] O check-in só pode ser validado até 20 minutos após ser criado;
- [x] O check-in só pode ser validado por administradores;
- [x] A academia só pode ser cadastrada por administradores;

### RNFs (Requisitos não-funcionais)

- [x] A senha do usuário precisa estar criptografada;
- [x] Os dados da aplicação precisam estar persistidos em um banco PostgreSQL;
- [x] Todas listas de dados precisam estar paginadas com 20 itens por página;
- [x] O usuário deve ser identificado por um JWT (JSON Web Token);

## Rotas
- Criar novo usuário
```bash
POST /users
```

- Faz a autenticação do usuário através do JWT
```bash
POST /sessions
```

- Faz a renovação do token do usuário
```bash
PATCH /token/refresh
```

- Busca o perfil do usuário  
```bash
GET /me
```

-  Busca academias por nome
```bash
GET /gyms/search
```

- Busca academias perto do usuário  
```bash
GET /gyms/nearby
```

- Faz a criação de uma academia (apenas usuário ADMIN)  
```bash
POST /gyms
```
-  Busca o histórico de check-ins de um usuário 
```bash
GET /check-ins/history
```

- Faz a busca do resumo de check-ins do usuário durante um período de tempo
```bash
GET /check-ins/metrics
```

- Faz o check-in de um usuário em uma academia  
```bash
POST /gyms/:gymId/check-ins
```
- Faz a validação de check-in de um usuário na academia por data e por horário (apenas usuário ADMIN)  
```bash
PATCH /check-ins/:checkInId/validate
```

## Testes automatizados (E2E)

  - [x] Should be able to refresh a token
  - [x] Should be able to create a check-in
  - [x] Should be able to get the total count of check-ins
  - [x] Should be able list nearby gyms
  - [x] Should be able to get user profile
  - [x] Should be able to register
  - [x] Should be able to list the history of check-ins
  - [x] Should be able to authenticate
  - [x] Should be able to validate a check-in
  - [x] Should be able to search gyms by title
  - [x] Should be able to create a gym

## Autor

[![Linkedin Badge](https://img.shields.io/badge/-LinkedIn-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/matheusgmello/)](https://www.linkedin.com/in/matheusgmello/)

Desenvolvido durante o bootcamp Ignite da [Rocketseat](https://rocketseat.com.br)💜
