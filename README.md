# Hello World CI/CD Deployment – GitLab & AWS EC2

This project demonstrates a full CI/CD pipeline using GitLab to build, test, and deploy a Dockerized Node.js app to an AWS EC2 instance.

## 🚀 Technologies
- Node.js + Express.js
- Docker + Docker Compose
- GitLab CI/CD
- AWS EC2 (Ubuntu)
- Jest (testing)

## 📁 Project Structure
hello-world/
│
├── app.js # Express server
├── app.test.js # Jest unit test
├── Dockerfile # Docker build instructions
├── docker-compose.yml # Service orchestration
└── .gitlab-ci.yml # GitLab pipeline config

bash
Copy
Edit

## 🛠 How to Run Locally

### 1. Clone the repo
```bash
git clone https://gitlab.com/it-works-on-my-machine1/hello-world.git
cd hello-world
2. Install dependencies
bash
Copy
Edit
npm install
3. Run the app
bash
Copy
Edit
node app.js
# Visit http://localhost:3000
4. Run tests
bash
Copy
Edit
npm test
5. Run with Docker (optional)
bash
Copy
Edit
docker build -t hello-world-app .
docker run -p 3000:3000 hello-world-app
📦 GitLab CI/CD
The pipeline consists of:

build: Docker image built and pushed to GitLab Registry

test: Jest unit tests run in isolated Node.js container

deploy: SSH to EC2 and start the container using docker-compose

🐧 EC2 Deployment
The final image is deployed to an AWS EC2 instance with Docker and Docker Compose pre-installed.

🧪 Test Info
Tests written in app.test.js

Use supertest and jest

One endpoint tested: /

