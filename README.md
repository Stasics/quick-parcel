# 🚚 Quick Parcel

> Веб-сервис для автоматизации работы курьерской службы с калькулятором доставки, трекингом и ролевой моделью.

---

## 📋 О проекте

**Quick Parcel** — это полноценное веб-приложение для управления процессом доставки. Система решает ключевые проблемы малых курьерских служб: ручной расчёт стоимости, отсутствие прозрачности статусов заказов и сложности с коммуникацией.

### 🎯 Основные возможности

- 👥 **Ролевая модель:** Клиент, Курьер, Администратор с разграничением прав доступа
- 🧮 **Калькулятор доставки:** Автоматический расчёт стоимости по весу и маршруту
- 📦 **Трекинг посылок:** Отслеживание статуса заказа в реальном времени
- ⚙️ **Админ-панель:** Управление пользователями, заказами и тарифами
- 📱 **Мобильная адаптация:** Работает на всех устройствах
- 🗺️ **Интеграция с картами:** Yandex Maps API

---

## 🛠️ Технологический стек

### Backend
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-FF6C37?style=for-the-badge&logo=sqlalchemy&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)

### Frontend
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

---

## 📁 Структура проекта
## 📁 Структура проекта
quick-parcel/
├── backend/ # Серверная часть (FastAPI)
│ ├── app/
│ │ ├── api/ # Эндпоинты (роутеры)
│ │ ├── core/ # Конфигурация, безопасность, JWT
│ │ ├── models/ # SQLAlchemy модели (БД)
│ │ ├── schemas/ # Pydantic схемы (валидация)
│ │ └── services/ # Бизнес-логика
│ ├── alembic/ # Миграции БД
│ ├── tests/ # Тесты
│ ├── Dockerfile
│ ├── requirements.txt
│ └── .env.example
│
├── frontend/ # Клиентская часть
│ ├── index.html # Главная страница
│ ├── css/
│ │ ├── style.css # Основные стили
│ │ └── admin.css # Стили админ-панели
│ ├── js/
│ │ ├── auth.js # Авторизация, регистрация
│ │ ├── packages.js # Управление посылками
│ │ ├── admin.js # Админ-панель
│ │ └── api.js # HTTP-запросы к бэкенду
│ └── assets/
│ └── images/ # Изображения, скриншоты
│
├── docker-compose.yml # Запуск всех сервисов
└── README.md


---

## 🚀 Быстрый старт

### Предварительные требования
- Python 3.10+
- PostgreSQL (или Docker)
- Git

### Вариант 1: Локальный запуск

**1. Клонируй репозиторий**
```bash
git clone https://github.com/Stasics/quick-parcel.git
cd quick-parcel
