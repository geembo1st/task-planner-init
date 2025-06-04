Task Planner — это многопользовательский планировщик задач с авторизацией, досками, задачами, email-уведомлениями и микросервисной архитектурой.
Каждый пользователь может планировать задачи на определённые дни. Уведомления отправляются через Kafka.

Функциональность:
- Регистрация и авторизация пользователей (JWT)
- Подтверждение email и рассылка уведомлений (через Kafka)
- Создание / редактирование / удаление задач
- Организация задач по доскам (каждая доска — под один день)
- Панель пользователя с задачами
- Уведомления на email о регистрации и входе
- Отдельная страница администратора для просмотра всех пользователей

Стек технологий:
- Backend: Java 17, Maven, Spring Boot (REST, Security, Kafka, Mail, Data JPA, Validation), JWT Token, PostgreSQL + Flyway, Kafka (Apache Kafka + Zookeeper)

- Frontend: JS, Thymeleaf, HTML, CSS

- DevOps: Docker, Docker Compose

Проект разделён на 5 микросервисов:

| Сервис                       | Назначение                                         | Порт   |
| ---------------------------- | -------------------------------------------------- | ------ |
| `TaskPlannerFrontendService` | Фронтенд на Thymeleaf                              | `3000` |
| `TaskPlannerApiGateway`      | API Gateway: маршрутизация запросов                | `8081` |
| `TaskPlannerBackendService`  | Бэкенд: логика пользователей, досок, задач, Kafka  | `8080` |
| `TaskPlannerEmailService`    | Отправка email через Kafka (регистрация, логин)    | `8082` |
| `TaskPlannerInitService`     | Сборка и запуск всех сервисов через Docker Compose | —      |

Ссылки на репозитории:
- https://github.com/geembo1st/task-planner-backend-service
- https://github.com/geembo1st/task-planner-email-service
- https://github.com/geembo1st/task-planner-api-gateway
- https://github.com/geembo1st/task-planner-frontend-service



