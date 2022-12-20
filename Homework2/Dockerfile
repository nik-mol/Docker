# берем базовый образ
FROM python:3.9-alpine

# копируем файл requirements.txt в директории src/requirements.txt
COPY ./requirements.txt /src/requirements.txt

# устанавливаем зависимости не кэшируя (--no-cache-dir)
RUN pip3 install --no-cache-dir --upgrade -r /src/requirements.txt

# копируем весь код из текущей директории внутрь папки src
COPY . /src

# открываем порт
EXPOSE 6060

# устанавливаем рабочую дирректорию src
WORKDIR src

# команды при запуске контейнера
CMD ["python", "manage.py", "runserver", "0.0.0.0:6060"]





