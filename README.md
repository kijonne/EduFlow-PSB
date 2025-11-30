# EduFlow

EduFlow — это образовательная платформа, разработанная для улучшения взаимодействия между студентами и преподавателями с использованием современных технологий и искусственного интеллекта.

## 👥 Команда

*   **Егор** — Frontend Developer
*   **Алиса** — Backend Developer
*   **Даша** — UI/UX Designer
*   **Кирилл** — System Analyst

## 📂 Структура проекта

Проект организован как монорепозиторий, содержащий клиентскую и серверную части.

```text
EduFlow/
├── backend/                # Серверная часть
│   ├── src/               # Исходный код (TypeScript)
│   │   ├── routes/        # API маршруты (Auth, Courses, AI, etc.)
│   │   ├── auth.ts        # Логика аутентификации
│   │   ├── db.ts          # Работа с базой данных SQLite
│   │   └── server.ts      # Точка входа сервера
│   ├── data/              # Файлы базы данных (игнорируются в git)
│   ├── Dockerfile         # Конфигурация сборки бэкенда
│   └── package.json       # Зависимости бэкенда
│
├── frontend/               # Клиентская часть
│   ├── src/               # Исходный код (React + TypeScript)
│   │   ├── components/    # UI компоненты
│   │   ├── pages/         # Страницы приложения
│   │   └── ...
│   ├── build/             # Результат сборки фронтенда
│   ├── Dockerfile         # Конфигурация сборки фронтенда
│   └── vite.config.ts     # Конфигурация Vite
│
├── docker-compose.yml      # Оркестрация контейнеров для запуска
└── README.md               # Документация проекта
```

## 🛠 Технологический стек

### Frontend
*   **Framework:** React 18
*   **Build Tool:** Vite
*   **Styling:** Tailwind CSS
*   **UI Components:** Radix UI, Lucide React
*   **Language:** TypeScript

### Backend
*   **Runtime:** Node.js (v20+)
*   **Framework:** Express
*   **Database:** SQLite (better-sqlite3)
*   **AI Integration:** Google Gemini API
*   **Language:** TypeScript

## 🚀 Запуск проекта

Для удобства запуска рекомендуется использовать Docker и Docker Compose.

### Предварительные требования
*   [Docker Desktop](https://www.docker.com/products/docker-desktop/) установлен и запущен.

### Инструкция по запуску

1.  **Клонируйте репозиторий:**
    ```bash
    git clone https://github.com/RuttiTuttii/EduFlow
    cd EduFlow
    ```

2.  **Настройка переменных окружения:**
    
    Для работы AI-функций убедитесь, что у вас есть API ключ для Google Gemini.
    В файле `docker-compose.yml` или через `.env` файл (в папке backend) можно задать необходимые переменные:
    *   `GEMINI_API_KEY`: Ваш ключ API.
    *   `JWT_SECRET`: Секрет для токенов (по умолчанию задан в коде для разработки).

3.  **Запуск приложения:**
    
    Выполните команду в корне проекта:
    ```bash
    docker-compose up --build
    ```
    
    *Эта команда соберет Docker-образы для фронтенда и бэкенда, установит зависимости и запустит сервисы.*

4.  **Доступ к приложению:**
    *   **Frontend:** [http://localhost:5173](http://localhost:5173)
    *   **Backend API:** [http://localhost:5000](http://localhost:5000)

### Локальный запуск (без Docker)

Если вы хотите запустить проект локально без контейнеризации:

**Backend:**
```bash
cd backend
npm install
# Убедитесь, что у вас установлен TypeScript
npm run build
npm start
```

**Frontend:**
```bash
cd frontend
npm install
npm run build
# Для запуска собранной версии
npm install -g serve
serve -s build -l 5173
# Или для режима разработки
npm run dev
```

## 📹 Демонстрация

Видео, демонстрирующее работоспособность прототипа: [Ссылка на Google Drive] https://drive.google.com/file/d/1JWrnTJCg3AinFrsmkh9HCnU_vRKKFzQL/view?usp=sharing
