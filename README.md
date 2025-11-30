#📦 Day 12 – Dockerizing a Python Flask Application

This project is part of my DevOps 90-Days Learning Plan, and on Day 12, I learned how to:

Build a Docker image for a Python application

Create a Dockerfile

Run the app inside a container

Tag and push the image to Docker Hub

#🚀 Project Overview

This is a simple Python Flask web application that returns:

Hello from Docker Container!


The project demonstrates how to containerize an app using Docker and run it consistently across different environments.

#📂 Project Structure
day12_docker_app/
├── app.py
├── requirements.txt
└── Dockerfile

#🧠 Files Explanation
1️⃣ app.py

Simple Flask application:

from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "Hello from Docker Container!"

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)

#2️ requirements.txt
flask

#3️⃣ Dockerfile
FROM python:3.10

WORKDIR /app

COPY . .

RUN pip install -r requirements.txt

EXPOSE 5000

CMD ["python", "app.py"]

🛠️ Building the Docker Image

Run:

docker build -t sonu-docker-app .

#▶️ Running the Container
docker run -p 5000:5000 sonu-docker-app


#App will run at:

👉 http://localhost:5000

👉 http://127.0.0.1:5000

#🐳 Tagging the Image
docker tag sonu-docker-app sonupd8294/sonu-docker-app:v1

#📤 Pushing to Docker Hub
docker push sonupd8294/sonu-docker-app:v1


#Docker Hub Repo:
🔗 https://hub.docker.com/r/sonupd8294/sonu-docker-app

#✅ Learning Outcome (Day 12)

By completing this project I learned:

✔ What Docker is
✔ How to create Dockerfile
✔ Building and tagging images
✔ Running containers
✔ Pushing images to Docker Hub
✔ Understanding container workflow
