# Start with a slim base image
FROM python:3.10-slim AS base

# Install system dependencies and update vulnerable packages
RUN apt-get update && apt-get upgrade -y && apt-get install -y --no-install-recommends \
    libexpat1=2.6.3-1 \
    zlib1g \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Install Flask and other Python dependencies
RUN pip install --no-cache-dir flask

# Set the working directory
WORKDIR /myapp

# Copy application code
COPY main.py /myapp/main.py

# Set the command to run the Flask application
CMD ["python", "/myapp/main.py"]
