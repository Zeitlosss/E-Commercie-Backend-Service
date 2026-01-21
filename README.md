# E-Commerce Backend

RESTful e-commerce backend with Spring Boot, JWT authentication, and Docker support.

## Quick Start

### Prerequisites
- Java 17+
- Maven 3.9+
- Docker & Docker Compose (optional)

### Run with Docker
```bash
docker-compose up -d
```
Access API at `http://localhost:8080`

### Run Locally
1. Start PostgreSQL:
```bash
docker run -d --name postgres -p 5432:5432 \
  -e POSTGRES_DB=ecommerce \
  -e POSTGRES_USER=postgres \
  -e POSTGRES_PASSWORD=postgres \
  postgres:15-alpine
```

2. Run application:
```bash
mvn spring-boot:run
```

## API Documentation
Swagger UI: http://localhost:8080/swagger-ui.html

## Default Endpoints

| Endpoint | Method | Access |
|----------|--------|--------|
| `/api/auth/register` | POST | Public |
| `/api/auth/login` | POST | Public |
| `/api/products` | GET | Public |
| `/api/categories` | GET | Public |
| `/api/orders` | POST | USER+ |
| `/api/users` | GET | ADMIN |

## Roles
- **USER** - Browse, order
- **MODERATOR** - Manage products/categories  
- **ADMIN** - Full access

## Testing
```bash
mvn test
```
