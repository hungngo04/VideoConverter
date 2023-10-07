FROM python:3.11.3-slim-bullseye

RUN apt-get update && apt-get install -y \
    gcc \
    libmariadb-dev \
    pkg-config \
    default-libmysqlclient-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app
COPY ./requirements.txt /app
RUN apt install pkg-config
RUN pip3 install --no-cache-dir --requirement /app/requirements.txt
COPY . /app

EXPOSE 5001

CMD ["python3", "server.py"]