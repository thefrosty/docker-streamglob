FROM python:3.7-alpine

RUN apk update \
    && apk add --no-cache $PHPIZE_DEPS \
    g++ \
    gcc \
    git \
    libxml2-dev \
    libxslt-dev \
    python3-dev \
    libffi-dev \
    libc-dev \
    libxslt-dev \
    openssl-dev \
    make

WORKDIR /usr/src/app

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

RUN mkdir -p ~/.config/streamglob

RUN git clone https://github.com/tonycpsu/streamglob \
    && cd streamglob \
    && pip install .

COPY . .
