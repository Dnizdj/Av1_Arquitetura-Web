# Av1_Arquitetura-Web


# Sistema de Gerenciamento de Produtos e Categorias

Este projeto é uma aplicação desenvolvida com **Spring Boot**, com foco na modelagem e persistência de dados utilizando **JPA** e banco de dados **MariaDB**. O objetivo é demonstrar o relacionamento entre entidades em um ambiente RESTful completo, com operações CRUD e boas práticas de desenvolvimento.

---

## Tecnologias Utilizadas

- Java 17+
- Spring Boot
- Spring Web
- Spring Data JPA
- Lombok
- MariaDB (via XAMPP)
- Maven

---

## Configuração do Ambiente

### 1. Banco de Dados (MariaDB)

- Instale e execute o XAMPP
- Inicie o serviço MySQL
- Acesse [phpMyAdmin](http://localhost/phpmyadmin)
- Crie um banco de dados chamado: `spring_demo`

### 2. Clonagem do Projeto

```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio
```

### 3. Configuração do `application.properties`

Local: `src/main/resources/application.properties`

```properties
spring.datasource.url=jdbc:mariadb://localhost:3306/spring_demo
spring.datasource.username=root
spring.datasource.password=
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MariaDBDialect
```

> Altere `username` e `password` conforme sua configuração local.

### 4. Execução da Aplicação

```bash
./mvnw spring-boot:run
```

ou

```bash
mvn spring-boot:run
```

---

## Estrutura de Entidades

### Categoria (`Categoria.java`)
- `id`: Long
- `nome`: String
- `produtos`: Lista de produtos associados (relacionamento OneToMany)

### Produto (`Produto.java`)
- `id`: Long
- `nome`: String
- `descricao`: String
- `preco`: double
- `categoria`: Categoria à qual o produto pertence (relacionamento ManyToOne)

### Relacionamento

- Uma categoria possui vários produtos (`@OneToMany`)
- Cada produto pertence a uma única categoria (`@ManyToOne`)
- Mapeamento é realizado via JPA com suporte automático à criação de chaves estrangeiras

---

## 📡 Endpoints REST

### Categorias

| Método | Endpoint           | Descrição              |
|--------|--------------------|------------------------|
| GET    | `/categorias`      | Listar categorias      |
| POST   | `/categorias`      | Criar nova categoria   |
| PUT    | `/categorias/{id}` | Atualizar categoria    |
| DELETE | `/categorias/{id}` | Remover categoria      |

### Produtos

| Método | Endpoint         | Descrição              |
|--------|------------------|------------------------|
| GET    | `/produtos`      | Listar produtos        |
| POST   | `/produtos`      | Criar novo produto     |
| PUT    | `/produtos/{id}` | Atualizar produto      |
| DELETE | `/produtos/{id}` | Remover produto        |

---

## Exemplos de Requisição

### Criar Categoria

```json
{
  "nome": "Informática"
}
```

### Criar Produto

```json
{
  "nome": "Mouse Gamer",
  "descricao": "Mouse com alta precisão",
  "preco": 199.99,
  "categoria": { "id": 1 }
}
```

---

## Validação e Testes

- Teste os endpoints via Postman ou Bruno
- Verifique o banco de dados no phpMyAdmin após cada operação
- Utilize as queries abaixo para validação manual:

```sql
SELECT * FROM categoria;
SELECT * FROM produto;
```

---

## Conclusão

Este sistema demonstra a implementação prática de:
- Relacionamento entre entidades utilizando JPA
- Integração com banco de dados relacional (MariaDB)
- Boas práticas com Lombok e organização modular
- APIs REST com operações CRUD completas
