# 📝 ToDoList - Gerenciador de Tarefas com Spring Boot  

Projeto desenvolvido como estudo de **Spring Boot** e boas práticas de desenvolvimento backend. Ele implementa um CRUD completo de tarefas (Create, Read, Update e Delete), autenticação básica e integração com banco de dados em memória (H2), além de já estar preparado para **deploy em containers Docker**. 🚀  

---

## 📌 Índice  

- [Sobre o projeto](#sobre-o-projeto)  
- [Como rodar](#como-rodar)  
- [Deploy](#deploy)  
- [Funcionalidades](#funcionalidades)  
- [Tecnologias utilizadas](#tecnologias-utilizadas)  
- [Estrutura do projeto](#estrutura-do-projeto)  
- [Rotas da API](#rotas-da-api)  
- [Licença](#licença)  

---

## 🔗 Sobre o projeto  

O **ToDoList** é uma API REST desenvolvida em **Java + Spring Boot**, projetada para gerenciar tarefas de usuários com autenticação e persistência de dados.  

O projeto foi construído seguindo boas práticas de arquitetura e código limpo, utilizando:  

- **Spring Web** para construção das rotas REST  
- **Spring Data JPA** para persistência de dados  
- **H2 Database** como banco de dados em memória  
- **BCrypt** para criptografia de senhas  
- **Dockerfile** configurado para deploy em serviços como Render  

O sistema permite que cada usuário gerencie suas próprias tarefas com segurança, garantindo que apenas o dono da tarefa possa editar ou deletá-la.  

---

## 🔧 Como rodar  

### 📋 Pré-requisitos  

- **Java 21+** ☕  
- **Maven** instalado  
- **Docker** (opcional, para execução em container)  

---

### ▶️ Rodando localmente  

1. Clone o repositório:  

```bash
git clone https://github.com/seu-usuario/todolist-spring-boot.git
cd todolist-spring-boot
```

2. Compile o projeto:  

```bash
mvn clean install
```

3. Execute a aplicação:  

```bash
mvn spring-boot:run
```

4. A aplicação estará disponível em:  

```txt
http://localhost:8080
```

---

### 🐳 Rodando com Docker  

1. Build da imagem:  

```bash
docker build -t todolist-spring .
```

2. Execute o container:  

```bash
docker run -p 8080:8080 todolist-spring
```

---

## ☁️ Deploy  

Este projeto está publicado na plataforma **Render** utilizando **Docker**.  

🔗 **Acesse a aplicação em produção:**  
👉 https://todolist-rocket-gdd3.onrender.com  

---

### 📌 Rotas principais  

| Método | Rota | Descrição |
|---|---|---|
| POST | `/users/` | Cadastro de usuário |
| POST | `/tasks/` | Criação de tarefas |
| GET | `/tasks/` | Listagem de tarefas |
| PUT | `/tasks/{id}` | Atualização de tarefa |
| DELETE | `/tasks/{id}` | Remoção de tarefa |

> As rotas de tarefas utilizam autenticação **Basic Auth**.  

---

## ✅ Funcionalidades  

- Cadastro de usuários com senha criptografada  
- CRUD completo de tarefas  
- Autenticação Basic Auth  
- Validação de regras de negócio  
- Tratamento global de exceções  
- Persistência com Spring Data JPA  
- Deploy com Docker + Render  

---

### 📌 Regras de validação  

- A data de início não pode ser anterior à data atual  
- A data de término deve ser maior que a data de início  
- O título da tarefa possui limite de 50 caracteres  
- Apenas o dono da tarefa pode editá-la ou removê-la  

---

## 🛠️ Tecnologias utilizadas  

<div align="center">

| Backend | Banco de Dados | DevOps |
|---|---|---|
| Java 21 | H2 Database | Docker |
| Spring Boot 3 | Spring Data JPA | Render |
| Spring Web | Hibernate | Maven |
| BCrypt |  |  |

</div>

---

## 📂 Estrutura do projeto  

```txt
todolist-spring-boot/
 ┣ 📂 src/main/java/br/com/hebertesteves/todolist
 ┃ ┣ 📂 user
 ┃ ┃ ┣ UserModel.java
 ┃ ┃ ┣ UserRepository.java
 ┃ ┃ ┗ UserController.java
 ┃ ┣ 📂 task
 ┃ ┃ ┣ TaskModel.java
 ┃ ┃ ┣ TaskRepository.java
 ┃ ┃ ┗ TaskController.java
 ┃ ┣ 📂 filter
 ┃ ┃ ┗ FilterTaskAuth.java
 ┃ ┣ 📂 utils
 ┃ ┃ ┗ Utils.java
 ┃ ┣ 📂 errors
 ┃ ┃ ┗ ExceptionHandlerController.java
 ┣ 📂 src/main/resources
 ┃ ┗ application.properties
 ┣ Dockerfile
 ┣ pom.xml
 ┗ README.md
```

---

## 🔀 Rotas da API  

### 👤 Usuários  

| Método | Endpoint | Descrição |
|---|---|---|
| POST | `/users/` | Criação de usuário |

---

### ✅ Tarefas  

| Método | Endpoint | Descrição |
|---|---|---|
| POST | `/tasks/` | Criação de tarefa |
| GET | `/tasks/` | Listagem das tarefas do usuário |
| PUT | `/tasks/{id}` | Atualização de tarefa |
| DELETE | `/tasks/{id}` | Exclusão de tarefa |

---

## 📜 Licença  

Este projeto está sob a licença **MIT**.  

Sinta-se livre para usar, estudar e contribuir. 🚀
