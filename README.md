# Produto API - Sistema para Gerenciamento de Produtos
Este projeto é uma aplicação backend para gerenciamento de produtos, utilizando Spring Boot e Flyway para controle de versão do banco de dados. O sistema possibilita a realização das operações CRUD (criar, ler, atualizar e excluir) de produtos no banco de dados.

## Funcionalidades
- Registro de novos produtos
- Edição de informações dos produtos
- Exclusão de produtos
- Exibição de lista de produtos
- Visualização dos detalhes de um produto
## Tecnologias Utilizadas
- **Spring Boot**: Framework para criação de aplicações em Java.
- **Flyway**: Ferramenta para controle de versões de banco de dados.
- **JPA (Java Persistence API)**: Utilizada para o mapeamento objeto-relacional e interação com o banco de dados.
- **MySQL**: Banco de dados utilizado para armazenamento das informações dos produtos.
- **Git**: Ferramenta para controle de versão do código-fonte.
## Instruções para Executar o Projeto
### 1. Requisitos
Certifique-se de que você possui as seguintes ferramentas instaladas no seu computador:

- **Java 17 ou versão superior**: [Download Java](https://www.oracle.com/java/technologies/javase-jdk17-downloads.html)
- **MySQL**: [Download MySQL](https://dev.mysql.com/downloads/installer/)
- **Maven**: [Download Maven](https://maven.apache.org/download.cgi)
### 2. Clonando o Repositório
Clone este repositório para o seu ambiente local:

### 3. Configurando o Banco de Dados
 - Abra o XAMPP e inicie o MySQL.

 - Crie o banco de dados utilizando o comando SQL:

CREATE DATABASE produto_db;
 - No arquivo src/main/resources/application.properties, configure a conexão com o banco de dados da seguinte forma:

spring.datasource.url=jdbc:mysql://localhost:3306/produto_db
spring.datasource.username=root
spring.datasource.password=
spring.jpa.hibernate.ddl-auto=update
### 4. Executando a Aplicação
Depois de configurar o banco de dados, execute o projeto utilizando o Maven com o comando:

mvn spring-boot:run
A aplicação será iniciada e estará disponível em: http://localhost:8080.

Endpoints Principais da API
Aqui estão os endpoints principais para o gerenciamento de produtos:

### 1. Listar Produtos
URL: /api/produtos
Método: GET
Descrição: Lista todos os produtos cadastrados.
Exemplo de cURL:
curl -X GET http://localhost:8080/api/produtos
### 2. Cadastrar Produto
URL: /api/produtos
Método: POST
Descrição: Cria um novo produto.
Corpo da Requisição (JSON):
{
  "nome": "Produto Exemplo",
  "descricao": "Descrição do produto",
  "preco": 29.99
}
Exemplo de cURL:
curl -X POST http://localhost:8080/api/produtos -H "Content-Type: application/json" -d '{"nome": "Produto Exemplo", "descricao": "Descrição do produto", "preco": 29.99}'
### 3. Detalhes de um Produto
URL: /api/produtos/{id}
Método: GET
Descrição: Exibe os detalhes de um produto específico.
Exemplo de cURL:
curl -X GET http://localhost:8080/api/produtos/1
### 4. Atualizar Produto
URL: /api/produtos/{id}
Método: PUT
Descrição: Atualiza as informações de um produto existente.
Corpo da Requisição (JSON):
{
  "nome": "Produto Atualizado",
  "descricao": "Descrição atualizada",
  "preco": 39.99
}
Exemplo de cURL:
curl -X PUT http://localhost:8080/api/produtos/1 -H "Content-Type: application/json" -d '{"nome": "Produto Atualizado", "descricao": "Descrição atualizada", "preco": 39.99}'
### 5. Excluir Produto
URL: /api/produtos/{id}
Método: DELETE
Descrição: Exclui um produto do banco de dados.
Exemplo de cURL:
curl -X DELETE http://localhost:8080/api/produtos/1
### Testes da API
Para testar os endpoints, você pode utilizar o Postman ou cURL diretamente no terminal. Veja os exemplos de cURL acima para testar as funcionalidades da API.

### Dependências do Projeto
 - Spring Web
 - Spring Data JPA
 - Driver MySQL
 - Flyway Migration
### Autor
Warley da Silveira Ostaque Filho

### Explicação do README.md:
1. **Descrição do Projeto**: Apresenta uma visão geral do sistema e das tecnologias utilizadas.
2. **Como Executar o Projeto**: Passos para clonar o repositório, configurar o banco de dados e rodar a aplicação.
3. **Endpoints da API**: Exemplos de como interagir com os principais endpoints utilizando cURL (GET, POST, PUT, DELETE).
4. **Instruções de Testes**: Como testar a API utilizando ferramentas como cURL ou Postman.
5. **Dependências**: As tecnologias necessárias para rodar a aplicação.
6. **Autor**: Informações sobre o criador do projeto.
