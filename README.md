# Blog7 Application

## Descrição

Este projeto é uma aplicação web utilizando SSR desenvolvida em .NET MVC(Model View Controller), utilizando ASP.NET Core para o backend e Entity Framework Core para o acesso ao banco de dados. A aplicação simula um sistema de blog onde os usuários podem criar, editar e visualizar posts. O sistema utiliza autenticação de usuários com sessões gerenciadas por cookies.

# Tecnologias Utilizadas

ASP.NET Core: Framework de desenvolvimento web.
Entity Framework Core: ORM para interações com o banco de dados.
PostgreSQL: Banco de dados relacional utilizado para armazenar as informações do blog.
Docker: Utilizado para orquestração dos serviços da aplicação, incluindo o banco de dados.
# Estrutura do Projeto

## Serviços
O projeto é composto apenas um serviço principal definido no arquivo docker-compose.yml:

db: Serviço do banco de dados PostgreSQL 14 no docker.

## Funcionalidades
Autenticação de Usuários: Os usuários podem se registrar e fazer login. A autenticação é baseada em cookies de sessão.
Gerenciamento de Posts: Criação, edição e exclusão de posts por usuários autenticados.
Exibição de Posts: Listagem e visualização de posts, com informações sobre o autor e a data de publicação.
Configuração e Execução

### Pré-requisitos
 - Docker e Docker Compose instalados na máquina.
 - .NET 8.0 Runtime instalado.

## Passos para Executar a Aplicação
 - Clone o repositório do projeto.
 - Navegue até o diretório do projeto e execute o comando:
'''docker-compose up''' -> O banco de dados estará disponível nas portas definidas no docker-compose.yml (5432).

'''dotnet restore'''

'''dotnet run'''

## Migrações de Banco de Dados
Para aplicar migrações e garantir que o banco de dados esteja atualizado, execute os seguintes comandos:

'''dotnet ef database update'''
## Estrutura do Código

### Controladores
 - PostController: Gerencia as operações relacionadas aos posts, como criação, edição, listagem e exclusão.
 - UserController: Gerencia as operações de autenticação, como login e registro de novos usuários.

### Modelos
- User: Representa um usuário no sistema.
- Post: Representa um post criado por um usuário.

### Autenticação
A autenticação é gerenciada utilizando cookies de sessão. O controlador UserController lida com o login e o armazenamento da sessão, enquanto o SessionStore gerencia as sessões em memória. Ademais todas as senhas são feitas em formato de hash.

