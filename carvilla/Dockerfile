# Use the official Apache HTTPD image as the base
FROM httpd:latest

# Add metadata about the image
LABEL Author="Harish"
LABEL Project="carvila"

# Set non-interactive environment
ENV DEBIAN_FRONTEND=noninteractive

# Update the system and install additional dependencies
RUN apt-get update && \
    apt-get install -y curl && \
    apt-get clean

# Expose port 80 for HTTP traffic
EXPOSE 80

# Set the working directory for the container
WORKDIR /usr/local/apache2/htdocs

# Declare a volume for persistent data
VOLUME ["/usr/local/apache2/htdocs"]

# Add the compressed tarball to the container and extract it
ADD carvilla.tar.gz /usr/local/apache2/htdocs

# Start the Apache server
CMD ["httpd-foreground"]

