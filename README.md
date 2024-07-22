# Сервис обмена валют с Telegram ботом

Этот проект состоит из двух основных компонентов:
1. Сервис получения курсов валют
2. Telegram бот для обмена валют

## Структура проекта

```
project_root/
├── currency_service/
│   └── ... (файлы сервиса курсов валют)
├── telegram_bot/
│   └── ... (файлы Telegram бота)
├── docker-compose.yml
└── .env.example
```

## Установка и запуск

1. Создайте файл `.env` в корневой директории проекта, используя `.env.example` как шаблон:
   ```
   cp .env.example .env
   ```

2. Отредактируйте файл `.env` и добавьте ваш токен Telegram бота:
   ```
   TELEGRAM_BOT_TOKEN=ваш_токен_здесь
   ```

3. Запустите проект с помощью Docker Compose:
   ```
   docker-compose up --build
   ```

## Использование

После запуска, бот будет доступен в Telegram. Вы можете использовать следующие команды:

- `/exchange <из_валюты> <в_валюту> <сумма>` - для конвертации валют
  Пример: `/exchange USD RUB 100`

- `/rates` - для получения текущих курсов основных валют

## Настройка

- В файле `.env` вы можете настроить следующие параметры:
  - `TELEGRAM_BOT_TOKEN` : токен вашего Telegram бота
  - `REDIS_HOST` : хост для Redis (по умолчанию "redis")
  - `REDIS_PORT` : порт для Redis (по умолчанию 6379)
  - `REDIS_DB` : номер базы данных Redis (по умолчанию 0)
