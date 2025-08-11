FROM python:3.11-slim

WORKDIR /workspace

COPY requirements.txt .   # <-- no ../ needed

RUN pip install --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt

COPY . .

RUN if [ ! -f .env ] && [ -f .env.example ]; then cp .env.example .env; fi
