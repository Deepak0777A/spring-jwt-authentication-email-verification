# 🔐 Spring Boot Authentication System (JWT + Email Verification)

A secure **Spring Boot 2.7** authentication system featuring **JWT-based login**, **email verification**, **Spring Security**, and **PostgreSQL**.

This project demonstrates a real-world authentication flow used in production-grade backend systems.

---

## 🚀 Features

- ✅ User Registration (Signup)
- 📧 Email Verification (Gmail SMTP)
- 🔑 Secure Login with JWT
- 🛡 Spring Security (Stateless)
- 🔐 Password Encryption (BCrypt)
- 🗄 PostgreSQL Database
- ⏳ Token Expiration Handling
- 🧪 REST APIs (JSON)

---

## 🧰 Tech Stack

- **Java 17**
- **Spring Boot 2.7.18**
- **Spring Security 5.7**
- **JWT (jjwt 0.11.5)**
- **PostgreSQL**
- **Hibernate / JPA**
- **Maven**
- **Gmail SMTP**
- **Lombok**

---

## 📁 Project Structure

src/main/java/com/example/demo
│
├── config # Security & JWT filters
├── controller # REST controllers
├── service # Business logic
├── repository # JPA repositories
├── model # Entities
└── dto # Request / Response objects


---

## 🔐 Authentication Flow

1. **Signup**
   - User registers with email & password
   - Password is encrypted using BCrypt
   - Verification code is sent via email

2. **Email Verification**
   - User verifies account using code

3. **Login**
   - Credentials authenticated using Spring Security
   - JWT token generated and returned

4. **Secure Requests**
   - JWT sent via `Authorization: Bearer <token>`
   - Requests validated by JWT filter

---

## 📌 API Endpoints

### 🔸 Signup
POST /auth/signup

```json
{
  "email": "user@gmail.com",
  "username": "user",
  "password": "password"
}
🔸 Login
POST /auth/login
{
  "email": "user@gmail.com",
  "password": "password"
}
🔸 Protected Endpoint Example
GET /test
Authorization: Bearer <JWT_TOKEN>
⚙️ Configuration
application.properties
# Server
server.port=8181

# Database
spring.datasource.url=jdbc:postgresql://localhost:5432/newdb
spring.datasource.username=postgres
spring.datasource.password=root

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

# JWT
security.jwt.secret-key=your_very_long_secure_secret_key_here
security.jwt.expiration-time=86400000

# Mail (Gmail SMTP)
spring.mail.host=smtp.gmail.com
spring.mail.port=587
spring.mail.username=your_email@gmail.com
spring.mail.password=your_app_password
spring.mail.properties.mail.smtp.auth=true
spring.mail.properties.mail.smtp.starttls.enable=true
⚠️ Use a Gmail App Password, not your real password.

▶️ Run the Project
mvn clean install
mvn spring-boot:run
App runs at:

http://localhost:8181
🔒 Security Notes
JWT secret key must be ≥ 256 bits

Passwords are never stored in plain text

Stateless authentication (no sessions)

🧪 Tested With
Postman

IntelliJ IDEA

Java 17

PostgreSQL 14+

📌 Future Improvements
🔄 Refresh Tokens

👮 Role-Based Authorization

📱 Frontend Integration

🐳 Docker Support

☁️ Deployment (AWS / Render)

👤 Author
Deepak Antony

If you found this project helpful, feel free to ⭐ the repository!

