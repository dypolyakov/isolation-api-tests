# API-тесты с изоляцией

Обучающий проект, демонстрирующий **банковскую систему, построенную на микросервисной архитектуре**, с асинхронной обработкой операций и API Gateway для интеграции с внешними системами.

Основная цель проекта — продемонстрировать:

- микросервисную архитектуру;
- HTTP и gRPC API;
- асинхронную обработку с использованием Kafka;
- четкое разделение предметных областей (доменов);
- локальную инфраструктуру на базе Docker.

## Обзор проекта

Система моделирует базовые банковские процессы, такие как создание и обработка финансовых операций.

Она состоит из **двух основных доменов:**

- **Gateway Service** — единая точка входа для внешних клиентов.
- **Operations Service** — сервис асинхронной обработки банковских операций.

Дополнительные сервисы (`users`, `cards`, `accounts`) используются в качестве примеров внутренних сервисов, доступных через Gateway.

## Архитектура

### Общая архитектура

![Общая архитектура](./docs/architecture/core.png)

### Gateway Service

![Gateway Service](./docs/architecture/gateway.png)

### Operations Service

![Operations Service](./docs/architecture/operations.png)

## Используемые технологии

- Python 3.12
- FastAPI (HTTP)
- gRPC
- Kafka
- PostgreSQL
- SQLAlchemy (асинхронный режим)
- Alembic
- Docker / Docker Compose

## Установка и запуск

### Предварительные требования

- Docker
- Docker Compose

### Сборка базового образа

```shell
docker build -t base-service .
```

### Запуск сервисов

```shell
docker-compose up -d
```

## Доступные сервисы

- Gateway HTTP: http://localhost:8001
- Gateway gRPC: localhost:9001
- Operations HTTP: http://localhost:8002
- Operations gRPC: localhost:9002
- Kafka UI: http://localhost:8081
- pgAdmin: http://localhost:5050
