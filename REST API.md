## REST API

### Два публичных REST API.

- Petstore SwaggerAPI - https://petstore.swagger.io/ 

- GitHub API - https://docs.github.com/ru/rest/repos

### Сравнительная таблица:

| Критерий | Petstore SwaggerAPI           | GitHub API              |
|----------|-------------------------------|-------------------------|
| **Основные эндпоинты и поддерживаемые методы** | Основные эндпоинты: /pet, /store, /user.<br>Поддерживаются базовые REST-методы: GET, POST, PUT, DELETE.<br>Все операции простые и наглядные.| Основные эндпоинты: /repos, /users, /issues, /pulls и др.<br>Методы: GET, POST, PUT, PATCH, DELETE.<br>Методы используются в зависимости от бизнес-логики (например, PATCH для частичного обновления). |
| **Форматы запроса и ответа** | Запросы и ответы в формате JSON.<br>Структура данных простая, без глубокой вложенности.<br>Иногда используется form-data (например, для загрузки файлов). | Запросы и ответы в формате JSON.<br>Ответы часто содержат вложенные объекты и массивы.<br>Много полей, которые зависят от прав пользователя.|
| **Особенности авторизации и версии API** | Авторизация необязательна или условная (тестовый api_key).<br>API используется без строгих ограничений.<br>Фиксированная версия (например, /v2).| Авторизация обязательна (Personal Access Token или OAuth).<br>Токен передаётся в заголовке Authorization.<br>Версия API указывается через заголовки и URL (v3).|
| **Отличия в подходах к дизайну и структуре** |  API сделан как учебный пример.<br>Минимум бизнес-логики.<br>Поведение эндпоинтов предсказуемое.<br>Подходит для обучения и экспериментов.| API спроектирован для реального продукта.<br>Строгая бизнес-логика и правила доступа.<br>Чёткая структура ресурсов и связей между ними.<br>Требует внимательного изучения документации.|

### Пример JSON-ответа.

- GitHub REST API (https://docs.github.com/en/rest/users/users#get-a-user)

{
  "id": 1296269,
  "name": "Hello-World",
  "full_name": "octocat/Hello-World",
  "private": false,
  "owner": {
    "login": "octocat",
    "id": 1,
    "type": "User"
  },
  "html_url": "https://github.com/octocat/Hello-World",
  "description": "This your first repo!",
  "fork": false,
  "created_at": "2011-01-26T19:01:12Z",
  "updated_at": "2023-05-01T10:15:30Z"
}

Корневые ключи:

- id - integer;
- name - string;
- full_name - string;
- private - boolean;
- html_url - string (URL);
- description - string / null;
- fork - boolean;
- created_at - string (datetime);
- updated_at - string (datetime).

Вложенные ключи:

- owner - object;
- login - string;
- id - integer;
- type - string.

