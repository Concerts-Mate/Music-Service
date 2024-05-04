# Описание

Music-Service - микросервис, отвечающий за получение информации о плейлистах, альбомах и концертах, работающий по RestfulAPI.

# Документация

Документацию к API можно посмотреть по `/docs` запущенного сервера (там же можно делать запросы), а также [здесь](docs/openapi.json).

# Конфигурация

* `REDIS_HOST` - хост Redis (значение по умолчанию - `localhost`)
* `REDIS_PORT` - порт Redis (значение по умолчанию - `6379`)
* `REDIS_PASSWORD` - пароль для Redis (значение по умолчанию - `password`)
* `CONCERTS_EXPIRATION_TIME` - время в секундах, на которое будут кэшироваться ответы на запросы о получении информации о концертах (значение по умолчанию - `60`)
* `TRACK_LISTS_EXPIRATION_TIME` - время в секундах, на которое будут кэшироваться ответы на запросы о получении информации о плейлистах и альбомах (значение по умолчанию - `60`)

# Запуск Redis

```bash
docker compose up -d
```

# Создание виртуального окружения

```bash
poetry shell
```

```bash
poetry install
```

# Запуск микросервиса

```bash
uvicorn main:app
```

> Можно указать аргументы `--port` and `--host` (значения по умолчанию - 8000 and 127.0.0.1 соответственно)
