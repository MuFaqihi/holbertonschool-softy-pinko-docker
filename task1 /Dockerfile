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

# Install Flask via pip
RUN pip3 install --no-cache-dir flask

# Set working directory
WORKDIR /app

# Copy application code
COPY api.py .

# Define default command
CMD ["python3", "api.py"]
