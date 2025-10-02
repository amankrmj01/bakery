# Shah's Bakery Microservice Platform

## 🧁 Introduction
Welcome to the Shah's Bakery Microservice Platform repository! This platform provides an integrated and scalable system specifically designed for managing bakery operations driven by microservices.

Modern bakeries face numerous challenges like:
- Managing perishable inventory
- Coordinating orders
- Engaging customers with timely notifications
- Ensuring smooth payment and delivery workflows

Our modular microservice architecture offers a flexible, robust solution to meet these needs efficiently. Each microservice is focused on a key business domain, enabling independent development, deployment, and scaling for maximum agility.

---

## 🛠️ Microservice Architecture
The platform follows microservice architectural principles, with services communicating over REST APIs and built using the Spring Boot and Spring Cloud stack.

### Key Benefits:
- **Scalability**: Services scale independently based on load.
- **Resilience**: Failure isolation with robust error handling.
- **Modularity**: Domain-driven design for maintainability.
- **Rapid Deployment**: Faster development and CI/CD.
- **Technology Diversity**: Best tech choices per service.

---

## 🧩 Core Microservices

| Service              | Purpose                                                                |
|----------------------|------------------------------------------------------------------------|
| API Gateway          | Central routing, authentication, and request filtering/gateway         |
| Auth Service         | User authentication, authorization, and security token management      |
| Cart Service         | Shopping cart handling including item/session management and totals    |
| Eureka Server        | Service discovery for dynamic microservice location                    |
| Notification Service | Email, SMS, push notifications; templates and campaigns                |
| Order Service        | Order processing, status updates, and history management               |
| Payment Service      | Payment processing and gateway integration                             |
| Product Service      | Product catalogue, pricing, and stock management                       |

---

## ⚙️ Tools and Technologies

- **Spring Boot** – Rapid REST API development  
- **Spring Cloud Netflix Eureka** – Service registry and discovery  
- **Spring Cloud OpenFeign** – Declarative REST clients  
- **Spring Security (OAuth2 / JWT)** – Authentication and authorization  
- **Spring Data JPA + PostgreSQL** – Resilient data persistence  
- **Redis** – Caching and session state  
- **Quartz Scheduler** – Task and campaign scheduling  
- **AWS SNS** – Push notification delivery  
- **Twilio** – SMS messaging  
- **Thymeleaf** – Email template generation  
- **Spring Retry** – Resilient communication  
- **Spring Boot Actuator** – Metrics and health checks  
- **OpenAPI / Swagger** – API documentation  
- **JUnit 5 + Testcontainers** – Testing infrastructure  
- **Docker + Docker Compose** – Containerization and orchestration  

---

## 🚀 Getting Started

1. Clone this repository.
2. Configure each microservice's `application.yml` for database, messaging, and third-party credentials.
3. Build and run services independently or via Docker Compose.
4. Use the API Gateway as the central entry point.
5. Explore interactive API docs via Swagger UI.

---

## 📁 Repository Structure

bakery/ 
│ 
├── bakery_api_gateway/ # API Gateway routing and security 
├── bakery_auth_service/ # User auth 
├── bakery_cart_service/ # Shopping and session cart 
├── bakery_eureka_server/ # Service discovery server 
├── bakery_notification_service/ # Notifications, templates and campaigns 
├── bakery_order_service/ # Order processing & lifecycle 
├── bakery_payment_service/ # Payment gateway integration 
├── bakery_product_service/ # Product catalogue management

  
  
  
## 🔄 Ongoing Development

### Kafka Integration in Progress

We are currently working on integrating **Apache Kafka** into Shah's Bakery Microservice Platform to enhance real-time communication and event-driven architecture across services.

---

## 📡 Why Kafka?

Apache Kafka is a distributed event streaming platform that enables high-throughput, fault-tolerant, and scalable messaging between microservices.

### 🔧 Planned Benefits of Kafka Integration:

- **Event-Driven Architecture**: Services will publish and subscribe to events (e.g., order placed, payment confirmed, product restocked) for better decoupling and responsiveness.
- **Real-Time Updates**: Enables instant updates across services like inventory, notifications, and order tracking.
- **Scalability**: Kafka handles high volumes of data efficiently, supporting bakery growth and peak traffic.
- **Resilience**: Durable message storage and replay capabilities improve fault tolerance and recovery.
- **Audit and Traceability**: Kafka topics can serve as a reliable audit trail for business events.

---

## 🧱 Kafka Use Cases in the Platform

| Microservice           | Kafka Role                                                                 |
|------------------------|-----------------------------------------------------------------------------|
| Order Service          | Publishes events like `OrderPlaced`, `OrderCancelled`                      |
| Payment Service        | Subscribes to `OrderPlaced`, publishes `PaymentConfirmed`, `PaymentFailed` |
| Notification Service   | Subscribes to `PaymentConfirmed`, `OrderStatusUpdated` for customer alerts |
| Product Service        | Subscribes to `OrderPlaced` to update stock levels                         |
| Cart Service           | May publish `CartAbandoned` events for marketing campaigns                 |

---

## 🚀 Next Steps

- Define Kafka topics and event schemas.
- Configure Kafka brokers and producers/consumers in each service.
- Implement retry and dead-letter queues for failed message handling.
- Monitor Kafka metrics via Spring Boot Actuator and Prometheus.

Stay tuned as we roll out Kafka-powered features to make Shah's Bakery more responsive and intelligent!
