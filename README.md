#  Kittygram

## Описание

[![Main Kittygram workflow](https://github.com/LittleVyach/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/LittleVyach/kittygram_final/actions/workflows/main.yml)
[![Main Taski workflow](https://github.com/LittleVyach/taski-docker/actions/workflows/main.yml/badge.svg)](https://github.com/LittleVyach/taski-docker/actions/workflows/main.yml)

Kittygram — это современная социальная платформа для любителей котиков, позволяющая делиться фотографиями своих питомцев, оценивать чужих котов и вести интерактивный каталог. Проект решает задачу создания удобного комьюнити-сервиса с возможностью загрузки медиаконтента, фильтрации по достижениям и управления профилем. В его основе лежит связка Django REST Framework для бэкенда и React для фронтенда, упакованная в изолированные Docker-контейнеры с настроенным CI/CD на базе GitHub Actions.

1. Клонируйте репозиторий и перейдите в него:
```
git clone https://github.com/LittleVyach/kittygram_final.git
cd kittygram
```
2. Создайте файл .env в корне проекта со следующими переменными окружения:
```
POSTGRES_DB=taski
POSTGRES_USER=taski_user
POSTGRES_PASSWORD=taski_password
DB_HOST=db
DB_PORT=5432
SECRET_KEY=ваш_секретный_ключ_django
DEBUG=False
ALLOWED_HOSTS=localhost,127.0.0.1
```
3. Запустите проект с помощью Docker Compose:
```
docker compose up --build
```
4.Для локального запуска тестов выполните:
```
python -m venv venv
source venv/bin/activate
pip install -r backend/requirements.txt
pytest
```
# Примеры
Получить список всех котиков:
```
HTTP
GET /api/cats/
```
Добавить нового питомца:
```
HTTP
POST /api/cats/
Content-Type: application/json

{
  "name": "Барсик",
  "color": "Purple",
  "birth_year": 2020,
  "achievements": [1, 3]
}
```
