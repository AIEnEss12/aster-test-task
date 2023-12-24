# aster.todo

## Конфигурация приложения

1. Отредактируйте файл `application.properties` в директории `src/main/resources`, чтобы указать параметры вашей базы данных:

    ```properties
    spring.datasource.url=jdbc:postgresql://localhost:5432/название_базы_данных
    spring.datasource.username=ваше_имя_пользователя
    spring.datasource.password=ваш_пароль
    spring.jpa.hibernate.ddl-auto=update
    ```

## Запуск приложения

1. Откройте проект в вашей IDE (Integrated Development Environment).
2. Запустите метод `main` в классе, помеченном аннотацией `@SpringBootApplication`.
3. После успешного запуска, ваше приложение будет доступно по адресу `http://localhost:8081`.

## Дополнительная информация

Swagger docs:
http://localhost:8081/swagger-ui.html - home page
http://localhost:8081/v3/api-docs

Сущность Task:
  
Примеры HTTP-запросов:

GET /tasks - Получение всех задач
GET /tasks/{id} - Получение задачи по ID
POST /tasks - Создание новой задачи (тело запроса содержит JSON с полями userId, name и description)
PUT /tasks/{id} - Обновление задачи по ID (тело запроса содержит JSON с полями userId, name и description)
DELETE /tasks/{id} - Удаление задачи по ID, Добавил ограничение, возможность удаление только для роли admin


Сущность User

## Эндпоинты

### Регистрация нового пользователя
- **Метод:** POST
- **Путь:** `/register`
- **Описание:** Регистрирует нового пользователя в системе.

### Логин пользователя
- **Метод:** POST
- **Путь:** `/login`
- **Описание:** Метод, не предназначенный для вызова из приложения. Реализован Spring Security для обработки аутентификации.

### Смена пароля пользователя
- **Метод:** POST
- **Путь:** `/password`
- **Описание:** Обновляет пароль пользователя.

### Аутентификация пользователя
- **Метод:** POST
- **Путь:** `/authenticate`
- **Описание:** Аутентифицирует пользователя и создает токен доступа JWT.
