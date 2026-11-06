FROM python:3.9-slim

# Set the working directory inside the container
WORKDIR /app

# Copy all files from the current directory to the container's working directory
COPY . .

# Install dependencies from the requirements file without using cache to reduce image size
RUN pip install --no-cache-dir -r requirements.txt

# Define the command to start the application using Gunicorn with 4 worker processes.
# Since app.py is inside the backend directory in your GitHub Repo, we can specify "backend.app:superkart_api"
# or ensure Gunicorn runs from the correct python path using python's module path syntax.
CMD ["gunicorn", "-w", "4", "-b", "0.0.0.0:7860", "backend.app:superkart_api"]
