# Use official Python image
FROM python:3.10-slim

# Update and install git
RUN apt-get update && \
    apt-get install -y git && \
    rm -rf /var/lib/apt/lists/*

# Set working directory
WORKDIR /workspace

# Copy only dependency files initially
COPY requirements.txt .

# Upgrade pip and install Python dependencies
RUN pip install --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt

# Copy the rest of your project
COPY . .

# Ensure .env is not accidentally committed
RUN if [ ! -f .env ] && [ -f .env.example ]; then cp .env.example .env; fi

