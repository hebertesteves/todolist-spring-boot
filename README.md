# 📝 ToDoList - Gerenciador de Tarefas com Spring Boot  

Projeto desenvolvido como estudo de **Spring Boot** e boas práticas de desenvolvimento backend. Ele implementa um CRUD completo de tarefas (Create, Read, Update e Delete), autenticação básica e integração com banco de dados em memória (H2), além de já estar preparado para **deploy em containers Docker**. 🚀  

---

## 📌 Índice  
- [Sobre o projeto](https://github.com/hebertesteves/todolist-spring-boot#-sobre-o-projeto)  
- [Como rodar](https://github.com/hebertesteves/todolist-spring-boot#-como-rodar)  
- [Funcionalidades](https://github.com/hebertesteves/todolist-spring-boot#-funcionalidades)  
- [Tecnologias utilizadas](https://github.com/hebertesteves/todolist-spring-boot#%EF%B8%8F-tecnologias-utilizadas)  
- [Estrutura do projeto](https://github.com/hebertesteves/todolist-spring-boot#-estrutura-do-projeto)  
- [Rotas da API](https://github.com/hebertesteves/todolist-spring-boot#-tarefas)  
- [Licença](https://github.com/hebertesteves/todolist-spring-boot#-licença)  

---

## 🔗 Sobre o projeto  

O **ToDoList** é uma API REST desenvolvida em **Java + Spring Boot**, projetada para gerenciar tarefas de usuários com autenticação e persistência de dados.  

O projeto foi construído seguindo boas práticas de arquitetura e código limpo, utilizando:  

- **Spring Web** para construção das rotas REST.  
- **Spring Data JPA** para persistência de dados.  
- **H2 Database** como banco de dados em memória.  
- **BCrypt** para criptografia de senhas.  
- **Dockerfile** configurado para deploy em serviços como Render.  

O sistema permite que cada usuário gerencie suas próprias tarefas com segurança, garantindo que apenas o dono da tarefa possa editar ou deletar.  

---

## 🔧 Como rodar  

### Pré-requisitos  
- **Java 21+** ☕  
- **Maven** instalado  
- **Docker (opcional, para rodar em container)**  

### Rodando localmente  

1. Clone o repositório:  
   ```bash
   git clone https://github.com/seu-usuario/todolist-spring-boot.git
   cd todolist-spring-boot
   ```

2. Compile e rode com Maven:  
   ```bash
   mvn clean install
   mvn spring-boot:run
   ```

3. O projeto estará disponível em:  
   ```
   http://localhost:8080
   ```

### Rodando com Docker  

1. Build da imagem:  
   ```bash
   docker build -t todolist-spring .
   ```

2. Execute o container:  
   ```bash
   docker run -p 8080:8080 todolist-spring
   ```

## Deploy ☁️

Este projeto está publicado na plataforma **Render** utilizando **Docker**.  

🔗 Acesse a aplicação em produção:  
👉 [https://todolist-rocket-gdd3.onrender.com](https://todolist-rocket-gdd3.onrender.com)

📌 Rotas principais:
- `POST /users/` → cadastro de usuário  
- `POST /tasks/` → criação de tarefas (com autenticação Basic)  
- `GET /tasks/` → listar tarefas do usuário autenticado  
- `PUT /tasks/{id}` → atualizar tarefa  
- `DELETE /tasks/{id}` → remover tarefa  

---

## ✅ Funcionalidades  

- Cadastro de **usuários** com senha criptografada.  
- CRUD de **tarefas** (criar, listar, atualizar, deletar).  
- Validações:  
  - Data de início não pode ser anterior à data atual.  
  - Data de término deve ser maior que a de início.  
  - Título limitado a **50 caracteres**.  
- Apenas o dono da tarefa pode alterá-la ou removê-la.  
- Tratamento global de exceções.  

---

## 🛠️ Tecnologias utilizadas  

- **Java 21**  
- **Spring Boot 3**  
- **Spring Web**  
- **Spring Data JPA**  
- **H2 Database**  
- **BCrypt** (criptografia de senhas)  
- **Maven**  
- **Docker**
- **Render (Deploy)**

---

## 📂 Estrutura do projeto  

```
todolist-spring-boot/
 ┣ 📂 src/main/java/br/com/hebertesteves/todolist
 ┃ ┣ 📂 user        → Model, Repository e Controller de Usuários
 ┃ ┣ 📂 task        → Model, Repository e Controller de Tarefas
 ┃ ┣ 📂 filter      → Filtro de autenticação (Basic Auth)
 ┃ ┣ 📂 utils       → Classe utilitária para atualização parcial de entidades
 ┃ ┣ 📂 errors      → Tratamento global de exceções
 ┣ 📂 resources
 ┃ ┣ application.properties → Configuração do banco H2
 ┣ Dockerfile
 ┣ pom.xml
```

---

## 🔀 Rotas da API  

### Usuários  
- `POST /users/` → Criação de usuário  

### Tarefas  
- `POST /tasks/` → Criação de tarefa  
- `GET /tasks/` → Listagem de tarefas do usuário  
- `PUT /tasks/{id}` → Atualização de tarefa  
- `DELETE /tasks/{id}` → Exclusão de tarefa  

---

## 📜 Licença  

Este projeto está sob a licença **MIT** – sinta-se livre para usar, estudar e contribuir.  
