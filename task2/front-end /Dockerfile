# Use a stable and specific version of Nginx
FROM nginx:1.25-alpine

# Set working directory for clarity (optional but good practice)
WORKDIR /usr/share/nginx/html

# Copy static front-end files
COPY ./softy-pinko-front-end /usr/share/nginx/html/softy-pinko-front-end

# Replace default Nginx configuration
COPY ./softy-pinko-front-end.conf /etc/nginx/conf.d/default.conf
