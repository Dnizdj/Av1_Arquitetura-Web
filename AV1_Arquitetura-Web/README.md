
# 📦 Projeto de Avaliação com Spring Boot + MariaDB

Este projeto é uma API RESTful simples desenvolvida em Java com Spring Boot, utilizando MariaDB como banco de dados. O objetivo é gerenciar **Produtos** e suas respectivas **Categorias**, com operações CRUD completas.

## 🚀 Tecnologias Utilizadas

- Java 17+
- Spring Boot
- Spring Data JPA
- Lombok
- MariaDB
- Maven

## 🗂 Estrutura do Projeto

```
src
└── main
    ├── java
    │   └── com.seuprojeto.avaliacao
    │       ├── AvaliacaoApplication.java
    │       ├── model
    │       │   ├── Categoria.java
    │       │   └── Produto.java
    │       ├── repository
    │       │   ├── CategoriaRepository.java
    │       │   └── ProdutoRepository.java
    │       └── controller
    │           ├── CategoriaController.java
    │           └── ProdutoController.java
    └── resources
        └── application.properties
```

## 🔧 Como rodar o projeto

### 1. Clone o repositório

```bash
git clone https://github.com/seu-usuario/nome-do-repositorio.git
cd nome-do-repositorio
```

### 2. Configure o banco de dados MariaDB

Crie um banco chamado `avaliacao_db` no seu MariaDB (você pode usar o XAMPP, DBeaver, ou outro gerenciador).

```sql
CREATE DATABASE avaliacao_db;
```

### 3. Ajuste as credenciais no arquivo `application.properties`

```properties
spring.datasource.url=jdbc:mariadb://localhost:3306/avaliacao_db
spring.datasource.username=SEU_USUARIO
spring.datasource.password=SUA_SENHA
```

### 4. Rode a aplicação

Você pode rodar com o comando Maven:

```bash
./mvnw spring-boot:run
```

Ou abrir no seu IDE favorito (VS Code, IntelliJ, etc) e rodar a classe `AvaliacaoApplication`.

## 🧪 Endpoints Disponíveis

### Categoria

- `GET /categorias` – Lista todas as categorias
- `POST /categorias` – Cria uma nova categoria

### Produto

- `GET /produtos` – Lista todos os produtos
- `POST /produtos` – Cria um novo produto

## ✍️ Autor

Desenvolvido por [Rafael Henrique Cardoso Mota](https://github.com/RafaelHMota) — sinta-se livre para contribuir e melhorar o projeto!
