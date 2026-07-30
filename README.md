# Spring Boot CRUD API with File-Backed H2

This project demonstrates a simple CRUD REST API using Spring Boot, Spring Web, Spring Data JPA, validation, and an embedded H2 database persisted to a local file.

## Requirements

- Java 17 or newer
- Maven 3.9 or newer

## Run

```bash
mvn spring-boot:run
```

The API runs at:

```text
http://localhost:8080
```

The H2 database is file-backed and will be created at:

```text
./data/crud-h2-file-demo.mv.db
```

H2 console:

```text
http://localhost:8080/h2-console
```

Use these console settings:

```text
JDBC URL: jdbc:h2:file:./data/crud-h2-file-demo;DB_CLOSE_ON_EXIT=FALSE
User Name: sa
Password:
```

## Endpoints

```text
GET    /api/products
GET    /api/products/{id}
POST   /api/products
PUT    /api/products/{id}
DELETE /api/products/{id}
```

## Example Requests

Create a product:

```bash
curl -X POST http://localhost:8080/api/products \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Keyboard",
    "description": "Mechanical keyboard",
    "price": 79.99,
    "quantity": 15
  }'
```

List products:

```bash
curl http://localhost:8080/api/products
```

Get a product:

```bash
curl http://localhost:8080/api/products/1
```

Update a product:

```bash
curl -X PUT http://localhost:8080/api/products/1 \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Keyboard Pro",
    "description": "Hot-swappable mechanical keyboard",
    "price": 99.99,
    "quantity": 8
  }'
```

Delete a product:

```bash
curl -X DELETE http://localhost:8080/api/products/1
```

## Test

```bash
mvn test
```
