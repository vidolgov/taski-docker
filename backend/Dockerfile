FROM python:3.10

WORKDIR /app

# Устанавливаем Gunicorn до копирования зависимостей
RUN pip install gunicorn==20.1.0

# Копируем файл зависимостей
COPY requirements.txt .

# Устанавливаем зависимости проекта
RUN pip install -r requirements.txt --no-cache-dir

# Копируем весь проект
COPY . .

# Запускаем Gunicorn
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]
