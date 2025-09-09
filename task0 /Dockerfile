# Step 1: Use a stable and specific Ubuntu base image
FROM ubuntu:22.04

# Step 2: Update package list and upgrade installed packages
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Step 3: Define the default command to run when the container starts
CMD ["echo", "Hello, World!"]
