FROM python:3.11-slim

# Set the working directory inside the container
WORKDIR /app

RUN apt-get update && apt-get install -y curl

RUN apt-get clean

# Copy the app code into the container
COPY main.py .
COPY requirements.txt .

# Install FastAPI and Uvicorn
RUN pip install -r requirements.txt

EXPOSE 8000

# Tell Docker how to run the app
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]