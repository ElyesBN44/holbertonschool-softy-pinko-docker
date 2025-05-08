# Use the latest official Ubuntu image
FROM ubuntu:latest

# Prevent interactive prompts during builds
ENV DEBIAN_FRONTEND=noninteractive

# Update system and install Python 3 & pip
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y python3 python3-pip && \
    rm -rf /var/lib/apt/lists/*

# Workaround for pip restrictions in Debian-based distros (if needed)
RUN rm -f /usr/lib/python*/EXTERNALLY-MANAGED || true

# Install Flask and flask-cors
RUN pip3 install --break-system-packages flask flask-cors

# Set working directory
WORKDIR /app

# Copy Flask app into container
COPY ./api.py .

# Expose port for Flask
EXPOSE 5252

# Run Flask app
CMD ["python3", "api.py"]
