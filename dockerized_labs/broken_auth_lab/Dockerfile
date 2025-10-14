FROM python:3.9-slim@sha256:aeebfa2890da7819f1617ec9a5650669570ab0802e5f51063aa8b7499da1ed26

WORKDIR /app

# Copy requirements first to leverage Docker cache
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application
COPY . .

# Set environment variables
ENV FLASK_APP=app.py
ENV FLASK_ENV=development
ENV PYTHONUNBUFFERED=1

# Expose port 5000
EXPOSE 5000

# Run the application
CMD ["python", "app.py"] 
