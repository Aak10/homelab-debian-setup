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
