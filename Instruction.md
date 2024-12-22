# INSTRUCTION FOR LAUNCH
## Измененение файлов
В zip - добавить нужные payments и transactions, а также features и labels (если имеются)

В main.ipynb прописать пути/названия новых файлов

## Используем базовый образ с Python
FROM python:3.9-slim

## Устанавливаем рабочую директорию в контейнере
WORKDIR /app

## Копируем файлы проекта в контейнер
COPY . .

## Устанавливаем зависимости
RUN pip install --no-cache-dir -r requirements.txt

## Устанавливаем переменные окружения
ENV PYTHONUNBUFFERED=1

## Указываем команду запуска
CMD ["python", "-m", "notebook", "main.ipynb"]
docker run -d --name hackk-runner -p 8888:8888 hackk-container

