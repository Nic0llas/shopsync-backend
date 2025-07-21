```markdown
# 🔧 ShopSync Backend

Sistema completo de estoque e vendas desenvolvido com **Spring Boot**, oferecendo autenticação JWT, controle de produtos, vendas, usuários, geração de relatórios e integração futura com IA via OpenAI.

---

## 📑 Índice

- [Sobre o Projeto](#sobre-o-projeto)
- [Funcionalidades](#funcionalidades)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Arquitetura](#arquitetura)
- [Instalação e Execução](#instalação-e-execução)
- [Configuração](#configuração)
- [API - Endpoints](#api---endpoints)
- [Segurança](#segurança)
- [Docker](#docker)
- [Testes](#testes)
- [Licença](#licença)
- [Contato](#contato)

---

## 🎯 Sobre o Projeto

O **ShopSync** é uma API RESTful para gerenciamento de vendas, produtos, usuários e relatórios, com autenticação baseada em JWT. Ideal para sistemas de ponto de venda, e-commerces ou gestão comercial.

---

## ✨ Funcionalidades

### 🔐 Autenticação e Autorização
- Registro e login com JWT
- Refresh token automático
- Controle por roles: `ADMIN` e `USER`
- Senhas com BCrypt

### 📦 Produtos
- Cadastro, listagem, atualização
- Estoque e preço
- Permissões por role

### 💰 Vendas
- Registro e histórico de vendas
- Permissões: `USER` vê suas vendas; `ADMIN` vê todas

### 📊 Relatórios
- Exportação em CSV
- Dados baseados no banco

### 📢 Notificações *(em desenvolvimento)*
- Gerenciamento por administradores

---

## ⚙️ Tecnologias Utilizadas

- **Java 21**
- **Spring Boot 3.2.3**
- **Spring Security / JWT**
- **Spring Data JPA**
- **Swagger (OpenAPI)**
- **MySQL 8.0** / H2 (testes)
- **Docker / Docker Compose**
- **Maven**

---

## 🏗 Arquitetura do Projeto

```

src/main/java/com/sistema/shop/
├── ChatbotVendasApplication.java
├── config/
├── controller/
├── model/
├── dto/
├── repository/
├── security/
└── service/

````

---

## 💻 Instalação e Execução

### 🔸 Requisitos
- Java 21+
- Maven 3.6+
- MySQL 8.0 (ou Docker)

### 🔸 Execução Local

```bash
git clone https://github.com/Nic0llas/shopsync-backend.git
cd shopsync-backend
mvn spring-boot:run
````

### 🔸 Execução com Docker

```bash
docker-compose up --build
```

---

## ⚙️ Configuração

### 🔐 Variáveis de ambiente (`.env`)

```env
JWT_SECRET=seu-segredo-jwt
JWT_REFRESH_SECRET=seu-refresh-segredo
OPENAI_API_KEY=chave-opcional-para-IA
```

### 💾 Banco de dados (`application.properties`)

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/shopsync_db
spring.datasource.username=root
spring.datasource.password=root
```

---

## 📡 API - Endpoints

### 🧑‍💼 Autenticação

* `POST /api/auth/register`
* `POST /api/auth/login`
* `POST /api/auth/refresh`

### 📦 Produtos

* `GET /api/products`
* `POST /api/products`
* `PUT /api/products`

### 💰 Vendas

* `GET /api/sales`
* `POST /api/sales`
* `DELETE /api/sales/{id}`

### 📊 Relatórios

* `GET /api/reports`

### 👥 Usuários

* `GET /api/users`

### 🔔 Notificações

* `PUT /api/notifications`

---

## 🔒 Segurança

* JWT com expiração e refresh
* Autorização por roles
* BCrypt para senhas
* Proteção em rotas via Spring Security
* Apenas `GET /api/products` e `/auth/**` são públicos

---

## 🐳 Docker

### Build manual

```bash
docker build -t shopsync-backend .
```

### Com Docker Compose

```bash
docker-compose up -d
```

---

## ✅ Testes

```bash
mvn test
mvn jacoco:report
```

---

## 📝 Licença

Este projeto está licenciado sob a [MIT License](LICENSE).

---

## 📞 Contato

Desenvolvedor: **Nicollas Silva**
Email: [nicollas.silva.santos.araujo@gmail.com](mailto:nicollas.silva.santos.araujo@gmail.com)
Repositório: [https://github.com/Nic0llas/shopsync-backend](https://github.com/Nic0llas/shopsync-backend)

---

> Última atualização: **21/07/2025** — Versão: 1.0.0

````