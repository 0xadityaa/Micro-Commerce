# E-Commerce Microservices Project

## Overview

This project is an e-commerce application built using a microservices architecture. It consists of separate services for Products, Orders, Admin, and Image management, all orchestrated through an API Gateway.

## Project Architecture

<img width="567" alt="image" src="https://github.com/user-attachments/assets/b6331853-8fe9-4937-bcf5-89a9ae4e5f6c">

## Technical Stack

- **Framework**: Spring Boot
- **Containerization**: Docker
- **Message Broker**: Apache Kafka
- **Databases**: PostgreSQL (or other SQL databases)
- **API Gateway**: Spring Cloud Gateway
- **Frontend**: React.js using Vaadin for connecting to springboot

## Microservices

1. **Products Service**: Manages product information and inventory.
2. **Orders Service**: Handles order processing and management.
3. **Admin Service**: Provides administrative functionalities.
4. **Image Service**: Manages product images.

## Key Features

- Microservices architecture for scalability and maintainability
- Docker containerization for easy deployment and scaling
- API Gateway for centralized request handling
- Asynchronous communication between services using Kafka
- Separate databases for each microservice
- Frontend shopping cart functionality

## Database Schemas

### Products Table
- id (INT PRIMARY KEY)
- name (VARCHAR(255) NOT NULL)
- description (TEXT)
- price (DECIMAL(10,2) NOT NULL)
- stock (INT NOT NULL)
- image_id (VARCHAR(50) NOT NULL)

### Orders Table
- id (INT PRIMARY KEY)
- order_date (DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP)
- total_price (DECIMAL(10,2) NOT NULL)
- (Foreign Key references to Products for ordered items)

### Images Table (Optional)
- id (VARCHAR(50) PRIMARY KEY)
- name (VARCHAR(255))
- mime_type (VARCHAR(50))
- (Additional metadata fields as needed)

## Communication

- RESTful APIs for most service-to-service communication
- Kafka for asynchronous events (e.g., order placement, product deletion)

## Deployment

The entire application is deployable using Docker Compose, which sets up all microservices and their respective databases.

## Getting Started

1. Clone the repository
2. Navigate to the project root directory
3. Run `docker-compose up` to start all services
4. Access the application through the API Gateway endpoint

## License

This project is licensed under the MIT License.
