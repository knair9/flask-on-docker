# Flask on Docker

[![Development Build](https://github.com/knair9/flask-on-docker/actions/workflows/docker.yml/badge.svg)](https://github.com/YOUR_USERNAME/flask-on-docker/actions/workflows/docker.yml)

## Overview

This repository contains a containerized Flask web application deployed using Docker and Docker Compose. The project demonstrates a simplified version of a modern web backend architecture similar to the infrastructure used by Instagram. The application allows users to upload files through a web interface and retrieve them from the server. The stack includes Flask for application logic, Gunicorn as the WSGI server, Nginx as a reverse proxy, and PostgreSQL as the database. Docker ensures the development environment is reproducible and easy to run on any system.

## Demo

The animation below demonstrates running the development server, uploading a file through the `/upload` endpoint, and retrieving the file from the `/media/<filename>` endpoint.

![Demo](images/flask-on-docker-demo.gif)

## Build Instructions

### Clone the repository

git clone https://github.com/knair9/flask-on-docker.git  
cd flask-on-docker

### Start the development environment

docker compose up -d --build

This command builds the Docker containers and starts the services for the Flask application and PostgreSQL database.

### Access the application

Open the upload page in your browser:

http://localhost:5001/upload

Upload a file using the form. After uploading, the file can be accessed at:

http://localhost:5001/media/<filename>

### Stop the services

docker compose down

## Continuous Integration

This repository includes a GitHub Actions workflow that verifies the development environment builds successfully. The workflow runs `docker compose build` whenever code is pushed to the repository or a pull request is created. The badge at the top of this README shows the current build status.
