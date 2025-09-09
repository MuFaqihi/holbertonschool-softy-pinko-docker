# Use a stable and specific Ubuntu version for consistency
FROM ubuntu:22.04

# Avoid interactive prompts during package installation
ENV DEBIAN_FRONTEND=noninteractive

# Update package list, install Python3 and pip, then clean up to reduce image size
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    rm -rf /var/lib/apt/lists/*

# Remove externally managed environment notice to allow pip installs
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED || true

# Install Flask and Flask-CORS without caching to save space
RUN pip3 install --no-cache-dir flask flask-cors

# Set working directory
WORKDIR /app

# Copy Flask app into the container
COPY api.py .

# Expose the application port (optional but good practice)
EXPOSE 5252

# Run the Flask app
CMD ["python3", "api.py"]
