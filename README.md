# holbertonschool-softy-pinko-docker
# Use a stable and specific Ubuntu version
FROM ubuntu:22.04

# Avoid interactive prompts during package installation
ENV DEBIAN_FRONTEND=noninteractive

# Update package list, install Python and pip, then clean up
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    rm -rf /var/lib/apt/lists/*

# Remove externally managed environment notice to allow pip installs
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED || true

# Install Flask and Flask-CORS without caching
RUN pip3 install --no-cache-dir flask flask-cors

# Set working directory
WORKDIR /app

# Copy application code
COPY api.py .

# Define default command
CMD ["python3", "api.py"]
# Softy Pinko Docker Project

## 📌 Overview
This project demonstrates how to containerize and orchestrate a full-stack web application using **Docker** and **Docker Compose**.  
The application consists of:
- **Front-end**: Static website served via **Nginx**.
- **Back-end**: API server built with **Flask** (Python) and **Flask-CORS**.
- **Proxy server**: Nginx reverse proxy that routes requests to the appropriate service.
- **Load balancing**: Nginx load balancer distributing traffic between multiple API servers.

---

## 🛠 Requirements
Before starting, ensure you have:
- [Docker Desktop](https://www.docker.com/) installed on your local machine.
- Basic knowledge of Docker, Dockerfiles, and Docker Compose.
- Familiarity with Nginx configuration and Flask basics.

---


