# Minimal API - Bootcamp Avanade

API RESTful desenvolvida em .NET 8 como parte do Bootcamp Avanade | Backend e IA. O projeto demonstra a construção de uma API mínima, seguindo princípios de arquitetura limpa e utilizando tecnologias modernas para autenticação, acesso a dados e documentação.

## ✨ Funcionalidades

- **Autenticação e Autorização:** Sistema de login seguro utilizando JSON Web Tokens (JWT).
- **Gerenciamento de Administradores:** Operações CRUD (Criar, Ler, Atualizar, Deletar) para usuários administradores.
- **Gerenciamento de Veículos:** Operações CRUD para uma entidade de veículos.
- **Documentação Interativa:** Interface do Swagger (OpenAPI) para visualização e teste dos endpoints.

---

## 🚀 Tecnologias Utilizadas

Este projeto foi construído com as seguintes tecnologias:

- **[ASP.NET Core 8](https://dotnet.microsoft.com/pt-br/apps/aspnet):** Framework principal para a construção da API.
- **[Entity Framework Core 8](https://docs.microsoft.com/pt-br/ef/core/):** ORM para a persistência de dados.
- **[MySQL](https://www.mysql.com/):** Banco de dados relacional.
- **[Swashbuckle (Swagger)](https://github.com/domaindrivendev/Swashbuckle.AspNetCore):** Geração de documentação da API.
- **[Autenticação JWT](https://jwt.io/):** Implementação de autenticação baseada em tokens.

---

## ⚙️ Como Configurar e Rodar o Projeto

Siga os passos abaixo para executar o projeto em seu ambiente local.

### Pré-requisitos

- [.NET 8 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)
- Um servidor MySQL rodando (localmente ou em um container Docker).
- Uma ferramenta de gerenciamento de banco de dados (como MySQL Workbench ou DBeaver).

O próximo passo é a configuração do banco de dados. É necessário criar um banco de dados vazio em seu servidor MySQL com o nome `minimal_api`. Após a criação, a string de conexão no arquivo `appsettings.json` deve ser atualizada com suas credenciais de acesso.

```json
"ConnectionStrings": {
  "MySql": "Server=localhost;Port=3306;Database=minimal_api;Uid=seu_usuario;Pwd=sua_senha;"
}
````

Com a conexão devidamente configurada, as tabelas do banco de dados podem ser criadas através das migrations do Entity Framework. Execute o comando abaixo no terminal, na pasta Api, para aplicar a estrutura da base de dados.

Bash

dotnet ef database update

Executando a Aplicação

Após a configuração do ambiente, a API pode ser iniciada com o seguinte comando:

Bash

dotnet run

O terminal informará a URL em que a aplicação está rodando, geralmente em http://localhost:<porta>.

📚 Documentação da API (Endpoints)

A documentação interativa de todos os endpoints está disponível via Swagger. Após iniciar a aplicação, acesse a seguinte URL em seu navegador:

http://localhost:<porta>/swagger

Principais Endpoints

Autenticação

POST /admin/login: Realiza o login de um administrador e retorna um token JWT.

Administradores (/admin)

GET /admin: Retorna uma lista de todos os administradores. (Requer autorização)

GET /admin/{id}: Busca um administrador por ID. (Requer autorização)

POST /admin: Cria um novo administrador. (Requer autorização de Admin)

DELETE /admin/{id}: Deleta um administrador. (Requer autorização de Admin)

Veículos (/vehicles)

GET /vehicles: Retorna uma lista de todos os veículos. (Requer autorização)

GET /vehicles/{id}: Busca um veículo por ID. (Requer autorização)

POST /vehicles: Cria um novo veículo. (Requer autorização de Admin)

PUT /vehicles/{id}: Atualiza os dados de um veículo. (Requer autorização de Admin)

DELETE /vehicles/{id}: Deleta um veículo. (Requer autorização de Admin)
