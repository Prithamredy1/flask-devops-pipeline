# Flask DevOps CI/CD Pipeline

This project is a simple Flask web application deployed using a complete DevOps CI/CD pipeline. It demonstrates automation, containerization, continuous integration, and deployment using modern DevOps tools.

## 🚀 Tech Stack Used

* **Flask (Python Web Framework)**
* **Docker** – Containerization
* **Jenkins** – CI/CD automation
* **Git & GitHub** – Version control and source hosting
* **Pytest** – Automated unit testing

## 🧠 What This Project Demonstrates

✔ Building a Flask application
✔ Writing automated test cases
✔ Creating a Docker image
✔ Pushing Docker images to Docker Hub
✔ Automating CI/CD pipeline using Jenkins
✔ Triggering builds automatically on Git push

This makes it a great DevOps portfolio project.

## 📂 Project Structure

```
flask-devops-pipeline/
├── app.py
├── Dockerfile
├── Jenkinsfile
├── requirements.txt
└── tests/
    └── test_app.py
```

## 🧪 Running Tests

To run the automated unit tests locally:

```
pytest
```

## 🐳 Running the App with Docker

### 1️⃣ Build the Docker image

```
docker build -t flask-devops-app .
```

### 2️⃣ Run the container

```
docker run -p 5000:5000 flask-devops-app
```

Then visit:

```
http://127.0.0.1:5000
```

## 🔁 CI/CD Pipeline (Jenkins)

Jenkins automatically:

1. Pulls code from GitHub
2. Installs dependencies
3. Runs unit tests
4. Builds Docker image
5. Pushes image to Docker Hub
6. Deploys the updated container

## 🧑‍💻 Author

**Pritham Reddy**
DevOps Engineer in Progress 🚀

## ⭐ Contribute

Feel free to fork this repo, open issues, or submit pull requests.
If you find this useful, consider giving the repo a ⭐ on GitHub!
