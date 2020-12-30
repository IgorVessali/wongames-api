# React Avançado - Won Games API

Esse projeto cria a API do ecommerce da Won Games do curso [React Avançado course](https://reactavancado.com.br/).

## Requirements

Esse projeto usa [PostgreSQL](https://www.postgresql.org/), portanto, para fazê-lo funcionar, instale em sua máquina local ou use Docker.
Também pode ser usado com SQLite.


A configuração do banco de dados pode ser encontrada em [config/database.js](config/database.js)

## Ambiente de desenvolvimento


Depois de clonar este projeto, instale as dependências:

```
yarn install
```

E execute usando:

```
yarn develop
```


Os urls para acessar são:

- `http://localhost:1337/admin` - O painel para criar e preencher dados
- `http://localhost:1337/graphql` - GraphQL Playground para testar o consumo da API

Na primeira vez para acessar o Admin, você precisará criar um usuário

## Buscar dados

This project uses a `/games/populate` route in order to populate the data via GoG site.
In order to make it work, follow the steps:

- Go to Roles & Permissions > Public and make sure `game:populate` route is public available and the upload as well
- With Strapi running run the following comand in your console:


Este projeto usa uma rota `/games/populate` para preencher os dados através do site GoG.
Para que funcione, siga os passos:

- Vá para Funções e permissões> Público e certifique-se de que a rota `game: populate` está disponível publicamente e o upload também
- Com o Strapi em execução, execute o seguinte comando em seu console:

```bash
$ curl -X POST http://localhost:1337/games/populate

# você pode passar parâmetros de consulta como:
$ curl -X POST http://localhost:1337/games/populate?page=2
$ curl -X POST http://localhost:1337/games/populate?search=simcity
$ curl -X POST http://localhost:1337/games/populate?sort=rating&price=free
```
