# 📚 LibroAPI

A Go-based **Bookstore REST API** built with **Clean Architecture** principles.  
It features PostgreSQL integration, Dockerized deployment, and a full testing setup — designed to demonstrate scalable backend design and maintainable coding practices.

---

## 🚀 Features
- ✅ Clean Architecture (layered & testable design)
- ✅ RESTful API for managing books and users
- ✅ PostgreSQL as the database
- ✅ Docker & Docker Compose for easy setup
- ✅ Unit and integration tests
- ✅ CI/CD ready (extendable)

---

## 🛠️ Tech Stack
- **Language:** Go (Golang)
- **Framework:** net/http, chi/gorilla/mux (depending on repo)
- **Database:** PostgreSQL
- **Containerization:** Docker & Docker Compose
- **Testing:** Go testing framework
- **Architecture:** Clean Architecture

---

## 📂 Project Structure
```
├── cmd/               # Application entry point
├── internal/          # Core business logic (domain, use cases, repositories)
├── pkg/               # Shared utilities/helpers
├── db/                # Database migrations/scripts
├── tests/             # Unit & integration tests
├── Dockerfile
├── docker-compose.yml
├── .env.example
└── README.md
```

---


## Description

This is an example of implementation of Clean Architecture in Go (Golang) projects.

Rule of Clean Architecture by Uncle Bob

- Independent of Frameworks. The architecture does not depend on the existence of some library of feature laden software. This allows you to use such frameworks as tools, rather than having to cram your system into their limited constraints.
- Testable. The business rules can be tested without the UI, Database, Web Server, or any other external element.
- Independent of UI. The UI can change easily, without changing the rest of the system. A Web UI could be replaced with a console UI, for example, without changing the business rules.
- Independent of Database. You can swap out Oracle or SQL Server, for Mongo, BigTable, CouchDB, or something else. Your business rules are not bound to the database.
- Independent of any external agency. In fact your business rules simply don’t know anything at all about the outside world.

More at https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html

This project has 4 Domain layer :

- Models Layer
- Repository Layer
- Usecase Layer
- Delivery Layer

#### The diagram:

![golang clean architecture](https://github.com/Anshul3914/LibroAPI/raw/master/clean-arch.png)

The original explanation about this project's structure can read from this medium's post : https://medium.com/@imantumorang/golang-clean-archithecture-efd6d7c43047.
It may be different already, but the concept still the same in application level, also you can see the change log from v1 to current version in Master.

### How To Run This Project

> Make Sure you have run the article.sql in your mysql

Since the project is already use Go Module, I recommend to put the source code in any folder but GOPATH.

#### Run the Testing

```bash
$ make tests
```

#### Run the Applications

Here is the steps to run it with `docker-compose`

```bash
#move to directory
$ cd workspace

# Clone into your workspace
$ git clone https://github.com/Anshul3914/LibroAPI.git

#move to project
$ cd libroapi

# copy the example.env to .env
$ cp example.env .env

# Run the application
$ make up

# The hot reload will running

# Execute the call in another terminal
$ curl localhost:9090/articles
```

### Tools Used:

In this project, I use some tools listed below. But you can use any similar library that have the same purposes. But, well, different library will have different implementation type. Just be creative and use anything that you really need.

- All libraries listed in [`go.mod`](https://github.com/Anshul3914/LibroAPI/blob/master/go.mod)
- ["github.com/vektra/mockery".](https://github.com/vektra/mockery) To Generate Mocks for testing needs.

---

## 📡 API Endpoints (Examples)

| Method | Endpoint         | Description        |
|--------|------------------|--------------------|
| GET    | `/health`        | Health check       |
| GET    | `/books`         | Get all books      |
| GET    | `/books/{id}`    | Get book by ID     |
| POST   | `/books`         | Create a new book  |
| PUT    | `/books/{id}`    | Update book        |
| DELETE | `/books/{id}`    | Delete book        |

Test with curl:
```bash
curl http://localhost:9090/books
```

