# API

## Основные эндпоинты:

___
Пользователи (Users)  
####
GET /users – Получить список всех пользователей \
GET /users/{user_id} – Получить конкретного пользователя \
GET /users/{user_id}/tasks - Получить задачи пользователя \
POST /users – Создать нового пользователя \
PUT /users/{user_id} – Обновить данные пользователя \
DELETE /users/{user_id} – Удалить пользователя

Задачи (Tasks)
####
GET /tasks – Получить список всех задач \
GET /tasks/{task_id} – Получить задачу по ID \
POST /tasks – Создать новую задачу \
PUT /tasks/{task_id} – Обновить задачу \
DELETE /tasks/{task_id} – Удалить задачу 

Вложения (Attachments)
####
GET /tasks/{task_id}/attachments – Получить все вложения к задаче \
POST /tasks/{task_id}/attachments – Добавить вложение к задаче \
DELETE /attachments/{attach_id} – Удалить вложение

Теги (Tags)
####
GET /tags – Получить список всех тегов \
GET /tags/{tag_id} – Получить тег по ID \
POST /tags – Создать новый тег \
DELETE /tags/{tag_id} – Удалить тег

Назначение тегов к задачам (Task_Assignees)
####
GET /tasks/{task_id}/tags – Получить все теги задачи \
POST /tasks/{task_id}/tags/{tag_id} – Добавить тег к задаче \
DELETE /tasks/{task_id}/tags/{tag_id} – Удалить тег у задачи

Авторизация (Auth)
####
POST /auth/register – Регистрация нового пользователя \
POST /auth/login – Вход пользователя \
POST /auth/logout – Выход пользователя \
POST /auth/refresh – Обновление токена \
GET /auth/me – Получение данных текущего пользователя\