# Use a stable and specific Ubuntu version
FROM ubuntu:22.04

# Avoid interactive prompts during package installation
ENV DEBIAN_FRONTEND=noninteractive

# Update and install Python3 and pip3, then clean up to reduce image size
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
