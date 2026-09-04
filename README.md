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


---

### Архитектура

Проект построен по принципу **многослойной архитектуры** с четким разделением ответственности:

- **API Layer (роутеры)** — принимают HTTP-запросы, валидируют данные через Pydantic, возвращают ответы
- **Services Layer (бизнес-логика)** — содержит основную логику приложения, обрабатывает данные, вызывает репозитории
- **Models Layer (SQLAlchemy)** — описывает структуру таблиц в базе данных
- **Core Layer** — конфигурация, подключение к БД, JWT, хеширование паролей

Такое разделение обеспечивает чистоту кода, упрощает тестирование и позволяет легко расширять функциональность.

---

### Аутентификация и безопасность

- **Хеширование паролей** — bcrypt (соль + хеш)
- **Аутентификация** — JWT-токены с временем жизни 7 дней
- **Ролевая модель** — реализована через поля `is_admin` и `is_courier` в модели пользователя
- **Защита эндпоинтов** — кастомные зависимости FastAPI (`Depends(require_admin)`, `Depends(get_current_user)`)
- **CORS** — настроен для безопасного взаимодействия с фронтендом

---

### База данных

Используется **PostgreSQL** в качестве основной СУБД. Работа с БД организована через **SQLAlchemy ORM** с асинхронным драйвером **asyncpg**.

**Основные таблицы:**

- `users` — пользователи (id, email, hashed_password, full_name, phone, is_active, is_admin, is_courier, created_at)
- `packages` — посылки (id, tracking_number, destination_pvz, from_address, weight, price, urgency, status, user_id)

Связи: `packages.user_id` → `users.id` (один пользователь может иметь много посылок)

---

### CI/CD Pipeline

Настроен автоматический конвейер через **GitHub Actions**:

- **Линтинг** — flake8, black (проверка стиля кода)
- **Тестирование** — pytest + pytest-cov (покрытие >85%)
- **Сборка** — Docker (сборка образов бэкенда и фронтенда)
- **Публикация** — GitHub Container Registry (публикация образа)
- **Деплой** — SSH + docker-compose (автоматическое развертывание на сервере)
---

## 📸 Скриншоты

### Главная страница
![Главная страница](https://github.com/Stasics/quick-parcel/blob/main/frontend/assets/images/1.png)

*Скриншот главной страницы с калькулятором и информацией о сервисе*

---

### Личный кабинет пользователя
![Личный кабинет](https://github.com/Stasics/quick-parcel/blob/main/frontend/assets/images/3.1.png?raw=true)
![Личный кабинет](https://github.com/Stasics/quick-parcel/blob/main/frontend/assets/images/3.2.png?raw=true)
*Страница с посылками пользователя и историей заказов*

---

### Админ-панель
![Админ-панель](https://github.com/Stasics/quick-parcel/blob/main/frontend/assets/images/4.1.png?raw=true)
![Админ-панель](https://github.com/Stasics/quick-parcel/blob/main/frontend/assets/images/4.png?raw=true)

*Управление пользователями, заказами и тарифами*

---

### Калькулятор доставки
![Калькулятор доставки](https://github.com/Stasics/quick-parcel/blob/main/frontend/assets/images/2.png?raw=true)

*Расчёт стоимости доставки по весу и маршруту*

---

## 🔮 Планы по развитию

- [ ] Мобильное приложение
- [ ] Telegram-бот для отслеживания
- [ ] Автоматическое построение маршрутов
- [ ] Система аналитики
- [ ] PWA (работа офлайн)

