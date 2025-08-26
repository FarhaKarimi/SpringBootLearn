---


# 🚀 Spring Boot Demo Project

این پروژه یک نمونه ساده با **Spring Boot** است که مفاهیم پایه‌ای زیر را پوشش می‌دهد:

- Auto-Configuration  
- Starter Dependencies  
- Profiles  
- Configuration Properties  
- Running App  
- Actuator & Health Checks  
- Spring MVC  
- HTTP Status Codes  
- Java Bean Validation  
- Controller Advice (Global Exception Handling)  

---

## ⚙️ تکنولوژی‌ها
- Java 17  
- Spring Boot 3.x  
- Maven  
- Spring Web  
- Spring Validation  
- Spring Actuator  

---

## 📂 ساختار پروژه
```

spring-boot-demo/
├── src/main/java/com/example/demo/
│    ├── DemoApplication.java
│    ├── controller/
│    │     ├── HelloController.java
│    │     ├── ProfileController.java
│    │     ├── ConfigController.java
│    │     └── UserController.java
│    ├── config/
│    │     └── AppProperties.java
│    ├── dto/
│    │     └── UserDTO.java
│    └── exception/
│          └── GlobalExceptionHandler.java
├── src/main/resources/
│    ├── application.yml
│    ├── application-dev.yml
│    └── application-prod.yml
└── pom.xml

````

---

## ▶️ نحوه اجرا
### 1. اجرا با Maven
```bash
mvn spring-boot:run
````

### 2. ساخت JAR و اجرا

```bash
mvn clean package
java -jar target/demo-0.0.1-SNAPSHOT.jar
```

---

## 🌐 Endpointها

### 1. Hello

```
GET http://localhost:8080/hello
```

### 2. Config Properties

```
GET http://localhost:8080/config
```

📌 خروجی: `My Spring App v1.0.0`

### 3. Profile (dev/prod)

```
GET http://localhost:8080/profile
```

با فعال کردن پروفایل:

```bash
java -jar target/demo-0.0.1-SNAPSHOT.jar --spring.profiles.active=dev
```

### 4. Actuator Health

```
GET http://localhost:8080/actuator/health
```

### 5. ایجاد کاربر

```
POST http://localhost:8080/users
Content-Type: application/json

{
  "name": "Ali",
  "email": "ali@example.com"
}
```

📌 پاسخ موفق:

```
201 Created
Saved user: Ali
```

### 6. اعتبارسنجی (Validation)

اگر داده اشتباه ارسال شود (مثلاً ایمیل خالی):

```
POST http://localhost:8080/users
{
  "name": "Ali",
  "email": ""
}
```

📌 پاسخ:

```
400 Bad Request
Validation error: Email must be valid
```

---


