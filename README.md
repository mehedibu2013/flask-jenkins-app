# 🚀 Flask Jenkins App

This is a simple Python Flask application that displays the current server time. The app is containerized with Docker and deployed automatically using Jenkins.

---

## 🧱 Project Structure

```

flask-jenkins-app/
├── app.py              # Flask app displaying current server time
├── Dockerfile          # Builds a container image for the app
├── requirements.txt    # Python dependencies
├── Jenkinsfile         # CI/CD pipeline definition
└── README.md

````

---

## 📦 Requirements

- Python 3.9+ (for local development)
- Docker
- Git
- Jenkins (installed locally or on a remote EC2 instance)

---

## ▶️ Run Locally with Docker

```bash
docker build -t flask-jenkins-app .
docker run -d -p 5000:5000 --name flask-container flask-jenkins-app
````

Open in your browser: [http://localhost:5000](http://localhost:5000)

---

## ⚙️ Jenkins CI/CD Pipeline

This project includes a `Jenkinsfile` for automated deployment using Jenkins. The pipeline:

1. Clones this GitHub repo
2. Builds a Docker image from `Dockerfile`
3. Runs the container on port 5000

### 🪛 Jenkins Setup Steps

1. Install Jenkins and Docker on your machine or EC2
2. Create a new Jenkins Pipeline job
3. Configure it to use your GitHub repository
4. Jenkins will pick the `Jenkinsfile` and run the build automatically

---

## 🌐 Live App Output

When accessed in browser:

```
Hello from Jenkins-deployed Flask app!
Current server time: 2025-05-30 21:35:00
```

---

## ✅ Git Ignore

This project ignores the `.venv/` directory to keep the repo clean.

---

## 🧪 To Do (Optional Enhancements)

* Add GitHub webhook for auto-trigger on push (Install & run ngrok to expose Jenkins (localhost:5000))
* Add unit tests with pytest
* Push image to AWS ECR or DockerHub
* Deploy to ECS, EKS, or EC2 via SSH in Jenkins

---

## 📄 License

MIT License

