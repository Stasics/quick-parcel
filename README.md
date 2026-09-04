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

## 🗺️ API Эндпоинты

| Метод | Эндпоинт | Описание | Доступ |
|-------|----------|----------|--------|
| **Аутентификация** ||||
| POST | `/api/auth/register` | Регистрация пользователя | Все |
| POST | `/api/auth/login` | Вход в систему | Все |
| GET | `/api/auth/me` | Информация о текущем пользователе | Все |
| PATCH | `/api/auth/me` | Обновление профиля | Все |
| **Посылки** ||||
| POST | `/api/packages/` | Создание посылки | Клиент |
| GET | `/api/packages/` | Список посылок пользователя | Все |
| GET | `/api/packages/{tracking}` | Информация о посылке | Все |
| PUT | `/api/packages/{tracking}/pay` | Оплата посылки | Клиент |
| PUT | `/api/packages/{tracking}/status` | Обновление статуса | Курьер/Админ |
| DELETE | `/api/packages/{tracking}` | Удаление посылки | Админ |
| **Администрирование** ||||
| GET | `/api/admin/packages/` | Все посылки (всех пользователей) | Админ |
| GET | `/api/admin/users/` | Список всех пользователей | Админ |
| PATCH | `/api/admin/users/{id}/role` | Изменение роли пользователя | Админ |
| GET | `/api/couriers` | Список всех курьеров | Админ |

📖 **Полная документация:** после запуска открой `http://localhost:8000/docs`

---

## 📸 Скриншоты

### Главная страница
![Главная страница](https://github.com/Stasics/quick-parcel/blob/main/frontend/assets/images/1.png)

*Скриншот главной страницы с калькулятором и информацией о сервисе*

---

### Личный кабинет пользователя
![Личный кабинет](https://via.placeholder.com/800x400/50C878/FFFFFF?text=Личный+кабинет+пользователя)

*Страница с посылками пользователя и историей заказов*

---

### Админ-панель
![Админ-панель](https://via.placeholder.com/800x400/FF6B6B/FFFFFF?text=Админ-панель)

*Управление пользователями, заказами и тарифами*

---

### Калькулятор доставки
![Калькулятор доставки](https://github.com/Stasics/quick-parcel/blob/main/frontend/assets/images/2.png?raw=true)

*Расчёт стоимости доставки по весу и маршруту*

---

## 🚀 Быстрый старт

### Предварительные требования

| Компонент | Требование |
|-----------|------------|
| **Python** | 3.10 или выше |
| **PostgreSQL** | 14 или выше |
| **Git** | Любая версия |
| **Docker** | (опционально) |

