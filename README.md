# 📘 Quote API with Rate Limiting

This is a simple RESTful API built using **Java Spring Boot** that returns a **random inspirational quote**.  
To ensure fair usage, it implements **IP-based rate limiting** using in-memory logic.

---

## 🚀 Features

- **Endpoint**: `GET /api/quote`
- **Returns**: JSON response with a random quote
- **Rate Limit**: 5 requests per minute per IP
- **Returns HTTP 429** when limit is exceeded
- Logs each request with client IP and status

---

## 🧰 Tech Stack

- Java 17
- Spring Boot 3.x
- Maven
- In-memory rate limiting with `ConcurrentHashMap`

---

## 🏗️ Project Structure

```
quote-api/
├── controller/
│   └── QuoteController.java
├── service/
│   └── QuoteService.java
├── ratelimiter/
│   └── RateLimiter.java
├── QuoteApiApplication.java
├── application.properties
├── pom.xml
└── README.md
```

---

## ⚙️ How to Run the Project

### ✅ Prerequisites
- Java JDK 17+ installed
- Maven installed
- VS Code or IntelliJ IDE

### ▶️ Steps
1. Download and extract the ZIP or clone the GitHub repo.
2. Open the folder in VS Code or IntelliJ.
3. Run the project:
   ```bash
   ./mvnw spring-boot:run
   ```
   Or on Windows:
   ```bash
   mvnw.cmd spring-boot:run
   ```
4. Open your browser or Postman and access:
   ```bash
   http://localhost:8080/api/quote
   ```

---

## 🧪 Example cURL Commands

### ✅ Valid Request:
```bash
curl http://localhost:8080/api/quote
```

### 🚫 Rate Limit Exceeded (After 5 requests/min):
```json
{
  "error": "Rate limit exceeded. Try again in 30 seconds."
}
```

---

## 📝 Assumptions & Design

- Quotes are hardcoded in memory (no DB).
- Rate limiting uses timestamps stored per IP.
- Uses synchronized access for thread safety.
- Suitable for simple, low-scale apps.

---

## 💡 Optional Enhancements (Bonus)

- Use **Bucket4j** or **resilience4j** for more robust rate limiting.
- Add **Swagger/OpenAPI** for documentation.
- Add **unit tests** for rate limiting.
- Custom rate limits per endpoint via annotation.

---

## 🧑‍💻 Author

- Developer: *Tegala Anantha Ramcharan*
- Submission: REST API Assessment with Spring Boot