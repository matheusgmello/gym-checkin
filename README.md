# Gympass API

A API foi desenvolvida com o propósito de simplificar o processo de check-in em academias, inspirando-se no modelo bem-sucedido do GYMPASS. Os usuários têm a opção de se registrar como MEMBER ou ADMIN.

# Configurações

### Requisitos

- [Node](https://nodejs.org/en/docs)
- [Docker](https://docs.docker.com/)

**Clone o projeto e acesse a pasta**

``` bash
git clone git@github.com:matheusgmello/gympass-solid-api && cd gympass-solid-api
```

- Instale as dependências(`npm run dev`)
- Configure o Docker(`docker compose up -d`)
- Copie o arquivo `env.example` e cole no (`.env`)
- Configure o banco de dados(`npm run knex -- migrate:latest`)
- Rode e teste a aplicação(`npm run start:dev`)

## Rotas

**Basta apenas baixar o arquivo e rodar no insomnia**

[![Run in Insomnia}](https://insomnia.rest/images/run.svg)](https://insomnia.rest/run/?label=GymSolid-API&uri=https%3A%2F%2Fraw.githubusercontent.com%2Fmatheusgmello%2Fgympass-solid-api%2Fmain%2FExport.json)


## Testes (E2E)

  -  `Deve ser capaz de atualizar um token.`
  -  `Deve ser capaz de criar um check-in.`
  - `Deve ser capaz de obter o total de check-ins`.
  -  `Deve ser capaz de listar as academias próximas.`
  -  `Deve ser capaz de obter o perfil do usuário.`
  -  `Deve ser capaz de se registrar.`
  -  `Deve ser capaz de listar o histórico de check-ins.`
  -  `Deve ser capaz de autenticar.`
  -  `Deve ser capaz de validar um check-in.`
  -  `Deve ser capaz de pesquisar as academias por título.`
  -  `Deve ser capaz de criar uma academia.`

## Tecnologias

- [Node](https://nodejs.org/en/docs)
- [Fastify](https://fastify.dev/docs/latest/)
- [Docker](https://docs.docker.com/)
- [Vitest](https://vitest.dev/)

<!--START_SECTION:footer-->
<br />

## 🔗 Connect with me
[![LinkedIn](https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/matheusgmello)
[![Reddit](https://img.shields.io/badge/Reddit-%23FF4500.svg?style=for-the-badge&logo=Reddit&logoColor=white)](https://www.reddit.com/user/math7zw)
[![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)](https://github.com/matheusgmello/)

<!--END_SECTION:footer-->