# 🌱 Automated Greenhouse Management System (AGMS)

A **Microservice-Based Smart Agriculture Platform** designed to automate and optimize greenhouse environmental conditions using real-time IoT data.

---

## 📌 Project Overview

The **Automated Greenhouse Management System (AGMS)** is a cloud-native distributed system that enables farmers to monitor and control greenhouse environments efficiently.

This system integrates with an external IoT data provider API to:
- Collect real-time temperature and humidity data  
- Process data using a rule-based engine  
- Trigger automated actions to maintain optimal conditions  

---

## 🎯 Objectives

- Manage greenhouse zones with custom environmental thresholds  
- Fetch real-time sensor data from external IoT APIs  
- Automate decisions (Fan ON / Heater ON) using rule engine  
- Track crop lifecycle and inventory  
- Implement scalable microservices architecture  

---

## 🏗️ System Architecture

This project follows a **Microservices Architecture** with:

### 🔧 Infrastructure Services
- Eureka Server – Service Discovery  
- API Gateway – Centralized routing & security  
- Config Server – Centralized configuration management  

### 🧩 Domain Microservices

| Service                     | Port | Description                                      |
|---------------------------|------|--------------------------------------------------|
| Zone Management Service   | 8081 | Manage greenhouse zones & thresholds            |
| Sensor Telemetry Service  | 8082 | Fetch IoT data & push to automation             |
| Automation Service        | 8083 | Rule engine & decision making                   |
| Crop Inventory Service    | 8084 | Manage crop lifecycle                           |

---

## 🧱 Technology Stack

| Component              | Technology |
|-----------------------|-----------|
| Infrastructure Services | Spring Boot 3.2.2, Spring Cloud 2023.0.0 |
| Service Discovery     | Netflix Eureka |
| API Gateway           | Spring Cloud Gateway + JWT |
| Config Server         | Spring Cloud Config (native profile) |
| Domain Services       | Spring Boot, OpenFeign, JPA/Hibernate |
| Databases             | H2 (default) / MySQL (optional) – polyglot persistence |
| External IoT API      | http://104.211.95.241:8080/api (JWT-protected) |

---

## 📂 Project Structure

├── eureka-server/

├── config-server/

├── api-gateway/

├── greenhouse-service/

├── irrigation-service/

├── monitoring-service/

└── README.md


---

## ▶️ Step-by-Step Startup Guide

⚠️ **IMPORTANT:** Start services in the correct order

---

### 1️⃣ Start Config Server (Port 8888)

cd config-server
mvn clean spring-boot:run

2️⃣ Start Eureka Server (Port 8761)

cd ../eureka-server
mvn clean spring-boot:run

3️⃣ Start API Gateway (Port 8080)

cd ../api-gateway
mvn clean spring-boot:run

4️⃣ Start Domain Services

🌿 Zone Service (Port 8081)

cd ../zone-service
mvn clean spring-boot:run

💧 Sensor Telemetry Service (Port 8082)

cd ../sensor-telemetry-service
mvn clean spring-boot:run

📊 Automation Service (Port 8083)

cd ../automation-service
mvn clean spring-boot:run

👨‍💻 Author

Ayusha Wijerathna
