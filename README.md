# README.md
# ⚡️ VibeControl: Lightweight Agentless Dashboard

**VibeControl** — это минималистичная панель управления серверами, созданная в рамках концепции "Zero-Agent". Она позволяет мониторить состояние удаленных узлов по SSH, не перегружая систему тяжелыми зависимостями и сложными фронтенд-фреймворками.

[![FastAPI](https://img.shields.io/badge/Backend-FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![HTMX](https://img.shields.io/badge/Frontend-HTMX-3366CC?style=flat-square)](https://htmx.org)
[![Docker](https://img.shields.io/badge/Infrastructure-Docker-2496ED?style=flat-square&logo=docker&logoColor=white)](https://www.docker.com)

---

## 🚀 Основные фишки
- **Agentless Architecture**: Никакого лишнего софта на целевых серверах — только стандартный SSH.
- **Modern Stack**: Сочетание скорости FastAPI и реактивности HTMX (SPA-опыт без лишнего JS).
- **Vibe UI**: Чистый темный интерфейс на Tailwind CSS, адаптированный под мобильные устройства.
- **DevOps Ready**: Полная контейнеризация "из коробки" для быстрого деплоя.

---

## 🛠 Технологический стек

- **Core:** Python 3.11 + FastAPI (Async)
- **SSH Engine:** Paramiko
- **UI/UX:** HTMX (AJAX-обновление компонентов) + Tailwind CSS
- **Templates:** Jinja2
- **Runtime:** Docker + Docker Compose

---

## 📦 Быстрый старт

### 1. Клонирование репозитория
```bash
git clone [https://github.com/sultank0909/vibe-control.git](https://github.com/sultank0909/vibe-control.git)
cd vibe-control

2. Запуск через Docker (Рекомендуется)
Проект полностью упакован. Просто запустите команду:

Bash
docker-compose up --build -d



3. Локальный запуск (для разработки)
Если нужно запустить без Docker:

Bash
pip install -r requirements.txt
uvicorn app.main:app --reload --port 8000


Конфигурация
На данный момент список серверов задается в app/main.py.
Для работы с реальными серверами убедитесь, что:

SSH-ключи проброшены в контейнер или указан путь к id_rsa.

IP-адреса серверов доступны из сети контейнера.


🗺 Roadmap (Планы по развитию)
[ ] Добавление поддержки WebSocket для real-time логов.

[ ] Интеграция SQLite для динамического управления списком серверов.

[ ] Кнопки быстрого действия (Restart Nginx, Clear Cache).

[ ] Авторизация через OAuth2 / Google.


Структура проекта
Plaintext
vibe-control/
├── app/
│   ├── main.py          # Логика FastAPI и SSH
│   ├── templates/
│   │   └── index.html    # Фронтенд (Tailwind + HTMX)
├── Dockerfile           # Упаковка в контейнер
├── docker-compose.yml   # Запуск одной командой
├── requirements.txt     # Зависимости
└── README.md            # "Лицо" проекта на GitHub
