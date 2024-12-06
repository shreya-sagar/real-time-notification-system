# Real-Time Notification System

## Description
This project is a **Spring Boot-based Real-Time Notification System** that leverages **WebFlux**, **Kafka**, **WebSocket**, **WebClient**, and **OAuth2** to provide secure, scalable, and reactive notifications. It integrates external services and provides real-time updates to connected clients.

---

## Features
- **Reactive APIs**: Built with Spring WebFlux for non-blocking, reactive programming.
- **Kafka Integration**: Asynchronous event-driven communication using Kafka.
- **WebSocket Notifications**: Real-time updates sent directly to connected clients.
- **OAuth2 Authentication**: Secure access with OAuth2 login.
- **External API Calls**: Enrich notifications with data from external APIs.

---

## Technologies Used
- **Spring Boot**: Backend framework.
- **Spring WebFlux**: Reactive programming.
- **Spring Kafka**: Kafka integration.
- **Spring Security**: OAuth2-based authentication.
- **WebSocket**: Real-time communication.
- **WebClient**: Non-blocking HTTP client.
- **Docker**: For Kafka setup.

---

## Prerequisites
- **Java 17+**
- **Apache Kafka** (set up locally or via Docker)
- **Maven** or **Gradle**
- An OAuth2 provider account (e.g., Google, GitHub)
- **Git** for version control

---

## Setup and Installation (JUST FOR FUTURE REFERENCE, IMPLEMENTATION IN PROGRESS)

### Clone the Repository
```bash
git clone https://github.com/yourusername/real-time-notification-system.git
cd real-time-notification-system
```

### Run Kafka
Start Kafka locally using Docker Compose:
```yaml
# docker-compose.yml example
version: '3.8'
services:
  zookeeper:
    image: 'confluentinc/cp-zookeeper:latest'
    ports:
      - '2181:2181'
    environment:
      ZOOKEEPER_CLIENT_PORT: 2181

  kafka:
    image: 'confluentinc/cp-kafka:latest'
    ports:
      - '9092:9092'
    environment:
      KAFKA_ZOOKEEPER_CONNECT: zookeeper:2181
      KAFKA_ADVERTISED_LISTENERS: PLAINTEXT://localhost:9092
      KAFKA_LISTENER_SECURITY_PROTOCOL_MAP: PLAINTEXT:PLAINTEXT
      KAFKA_OFFSETS_TOPIC_REPLICATION_FACTOR: 1
```
Run the following command:
```bash
docker-compose up
```

### Build and Run the Application
1. Build the application:
   ```bash
   mvn clean install
   ```
2. Run the application:
   ```bash
   mvn spring-boot:run
   ```

---

## API Endpoints
| Method | Endpoint                   | Description                    |
|--------|----------------------------|--------------------------------|
| `GET`  | `/login`                   | OAuth2 login endpoint.         |
| `POST` | `/notifications`           | Publish a notification event.  |
| `WS`   | `/ws/notifications`        | WebSocket endpoint for updates.|

---

## Future Enhancements
- Add a front-end for better user interaction.
- Enhance external API integration for richer notifications.
- Implement role-based access control with OAuth2 scopes.

---

## Contributing
Contributions are welcome! Please open an issue or submit a pull request for major changes.

---

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.



