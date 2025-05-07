# Use the latest Ubuntu base image
FROM ubuntu:latest

# Avoid interactive prompts during build
ENV DEBIAN_FRONTEND=noninteractive

# Update and upgrade the system
RUN apt-get update && apt-get upgrade -y

# Install Python3 and pip3
RUN apt-get install -y python3 python3-pip

# Remove EXTERNALLY-MANAGED file if it exists
RUN rm -f /usr/lib/python*/EXTERNALLY-MANAGED

# Install Flask using pip3
RUN pip3 install flask

# Set working directory to /app
WORKDIR /app

# Copy your Flask app into the container
COPY ./api.py /app/api.py

# Run the Flask app
CMD ["python3", "api.py"]
