# 🚀 PHP RabbitMQ Demo (Dockerized Microservices)

This is a **sample/demo project** demonstrating how two independent PHP applications communicate asynchronously using **RabbitMQ**.

The project is fully containerized using **Docker**, with no local PHP or Composer installation required.

---

## 🧱 Architecture

Producer (PHP) → RabbitMQ → Consumer (PHP)

* **Producer** sends messages (tasks)
* **RabbitMQ** acts as a message broker
* **Consumer** processes messages asynchronously

---

## ⚙️ Tech Stack

* PHP 8.2 (CLI)
* RabbitMQ (with Management UI)
* Docker & Docker Compose
* php-amqplib (RabbitMQ client)

---

## 📁 Project Structure

```
rabbitmq-demo/
├── docker-compose.yml
├── app1-producer/
│   ├── Dockerfile
│   ├── producer.php
│   ├── composer.json
├── app2-consumer/
│   ├── Dockerfile
│   ├── consumer.php
│   ├── composer.json
```

---

## ▶️ Getting Started

### 1. Clone the repository

```
git clone https://github.com/YOUR_USERNAME/php-rabbitmq-demo.git
cd php-rabbitmq-demo
```

---

### 2. Build and start containers

```
docker-compose up --build -d
```

---

### 3. Install dependencies (inside containers)

```
docker-compose run producer composer install
docker-compose run consumer composer install
```

---

### 4. Run Consumer

```
docker exec -it rabbit-mq-demo-consumer-1 php /app/consumer.php
```

---

### 5. Send Message (Producer)

```
docker exec -it rabbit-mq-demo-producer-1 php /app/producer.php
```

---

## 🧪 RabbitMQ Dashboard

Access the management UI:

```
http://localhost:15672
```

Login:

```
guest / guest
```

---

## 🎯 Features

* Asynchronous communication between services
* Message queue using RabbitMQ
* Fully Dockerized environment
* Composer runs inside container
* Simple producer-consumer pattern

---

## 📌 Use Case

This demo simulates real-world scenarios like:

* Order processing systems
* Email sending queues
* Background job processing
* Microservices communication

---

## 🚀 Future Improvements

* Retry mechanism
* Dead Letter Queue (DLQ)
* Multiple consumers (scaling)
* REST API → Queue integration
* Laravel queue integration

---

## 👨‍💻 Author

Aman Kumar

---

## ⭐ Note

This project is created as a **learning/demo project** to understand message queues and microservices communication using RabbitMQ.
