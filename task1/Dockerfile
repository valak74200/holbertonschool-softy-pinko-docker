# Use the latest version of Ubuntu as the base image
FROM ubuntu:latest

# Update APT package list and upgrade all packages
RUN apt-get update && apt-get upgrade -y

# Install Python3 and pip3
RUN apt-get install -y python3 python3-pip

# Remove externally managed environment restriction (if needed)
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED || true

# Install Flask using pip3
RUN pip3 install flask

# Set the working directory to /app
WORKDIR /app

# Copy the local Python script to the Docker image
COPY ./api.py /app/api.py

# Command to run the Flask application
CMD ["python3", "api.py"]
