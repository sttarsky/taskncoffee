# SQL-schema

База данных SQLite, движок *aiosqlite* 
___

### Структура базы данных:
#####
#### Users 

id - int, первичный ключ \
name - char, логин пользователя (уникально)\
password - varchar, пароль пользователя \
email - char, электронная почта для отправки уведомлений (не обязательно) \
telegram_id - bigint, id пользователя в телеграм для отправки уведомлений (не обязательно) \
avatar_path - varchar, путь до аватарки на диске (не обязательно)
#####
#### Tasks

Отношение многие к одному Users.
#####
id - int, первичный ключ \
user_id - int, relationship для Users.id \
title - char, заголовок задачи \
description - text, полное описание задачи (не обязательно) \
due_date - date, день недели на которое будет назначена задача \
status - enum, текущий статус задачи (open, closed, in progress, todo; по умолчанию open) \
priority - enum, приоритетность задачи (low, medium, high, critical) \
created_at - timestamp, время создания \
time_spent - int, затраченное время (по умолчанию - 0)
#####
#### Attachements

Отношение многие к одному Tasks.
####
id - int, первичный ключ \
task_id - int, relationship для Tasks.id \
file_path - varchar, путь до файла на диске \
uploaded_at - timestamp
#####
#### Tags

id - int, первичный ключ \
name - char, название тега (уникально)
#####
#### Task_Assignees
 
Отношение многие с многими Tasks - Tags
#####
id - int, первичный ключ \
task_id - int, relationship для Tasks.id \
tag_id - int, relationship для Tags.id
___
![db-schema.png](pics/db-schema.png)