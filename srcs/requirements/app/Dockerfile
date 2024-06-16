FROM python:3
ENV PYTHONUNBUFFERED 1
WORKDIR /app
COPY . .
RUN apt-get update
RUN pip install -r requirements.txt