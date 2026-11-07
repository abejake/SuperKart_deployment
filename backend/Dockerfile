FROM python:3.9-slim

# Set the working directory inside the container
WORKDIR /app

# Copy all files from backend_files to the working directory
COPY . .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Gunicorn starts app:superkart_api directly because app.py resides in the root /app directory of the container
CMD ["gunicorn", "-w", "4", "-b", "0.0.0.0:7860", "app:superkart_api"]
