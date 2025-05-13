# Microservices Architecture: Spring Boot + Eureka + API Gateway

This project demonstrates a microservices-based architecture using **Spring Boot**, **Spring Cloud Eureka**, and **Spring Cloud Gateway**.

## 🧩 Projects Overview

### 1. 🧭 Eureka Server (`eureka-server`)
- Acts as the **service registry** for all microservices.
- URL: `http://localhost:8761`

### 2. 🚪 API Gateway (`api-gateway`)
- Entry point for all client requests.
- Routes requests to other microservices using Eureka discovery.
- Port: `8080`
- Routes:
  - `/api/products/** → product-service`
  - `/api/orders/** → order-service`

### 3. 📦 Product Service (`product-service`)
- Handles product-related operations.
- Registers with Eureka.
- Port: `8081`
- Base URL via Gateway: `http://localhost:8080/api/products`

### 4. 🧾 Order Service (`order-service`)
- Manages order-related operations.
- Registers with Eureka.
- Port: `8082`
- Base URL via Gateway: `http://localhost:8080/api/orders`

---

## 🔧 Technologies Used
- Java 17 or 21
- Spring Boot 3.x
- Spring Cloud 2023.x
- Spring Cloud Eureka Server & Client
- Spring Cloud Gateway
- Maven

---

## 🚀 How to Run

### Prerequisites
- Java 17+ installed
- Maven installed

### 1. Start Eureka Server
```bash
cd eureka-server
mvn spring-boot:run
