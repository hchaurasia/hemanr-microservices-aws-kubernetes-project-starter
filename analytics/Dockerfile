FROM python:3.8-slim

ARG DB_PASS

WORKDIR /app

COPY . .

RUN apt update -y

RUN apt install build-essential libpq-dev -y

RUN pip install --upgrade pip setuptools wheel

RUN pip install -r requirements.txt

ENTRYPOINT python app.py


