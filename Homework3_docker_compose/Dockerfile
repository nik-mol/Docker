FROM python:3
# создание рабочей дирректории
WORKDIR /usr/src/app
# копирование requirements.txt в рабочую дирректорию
COPY requirements.txt /usr/src/app
# устанавливаем requirements.txt (зависимости)
RUN pip install -r requirements.txt
# копируем весь код из текущей директории внутрь рабочей дирректории
COPY . /usr/src/app
