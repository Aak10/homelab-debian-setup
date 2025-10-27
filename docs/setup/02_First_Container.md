# 02_First_Container.md

## Objective
Create and run the first Dockerized web app using Flask to understand the basics of containerization.

## Steps
1. Created `app.py` (simple Flask app).
2. Wrote `Dockerfile` to build a Python container image.
3. Built and ran the container.
4. Exposed port 5000 and tested via `curl` and browser.



## app.py

from flask import Flask
app = Flash(__name__)
@app.route('/')
def home():
    return "welcome to tron"

if __name__=='__main__':
    app.run(host='0.0.0.0' , port=5000)

## Commands
```bash
# Use an official lightweight Python base image
FROM python:3.9-slim

# Set working directory inside container
WORKDIR /app

# Copy files from current folder to /app
COPY . /app

# Install Flask inside the container
RUN pip install flask

# Expose the port Flask runs on
EXPOSE 5000

# Run the app when the container starts
CMD ["python", "app.py"]

