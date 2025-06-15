# Hello World CI/CD Deployment – GitLab & AWS EC2

This project demonstrates a full CI/CD pipeline using GitLab to build, test, and deploy a Dockerized Node.js app to an AWS EC2 instance.

## Technologies
- Node.js + Express.js
- Docker + Docker Compose
- GitLab CI/CD
- AWS EC2 (Ubuntu)
- Jest (testing)


## How to Run Locally

### 1. Clone the repo
git clone https://gitlab.com/it-works-on-my-machine1/hello-world.git
cd hello-world
### 2. Install dependencies
npm install
### 3. Run the app
node app.js
Visit http://localhost:3000
### 4. Run tests
npm test
### 5. Run with Docker (optional)
docker build -t hello-world-app .
docker run -p 3000:3000 hello-world-app

## GitLab CI/CD
The pipeline consists of:

build: Docker image built and pushed to GitLab Registry

test: Jest unit tests run in isolated Node.js container

deploy: SSH to EC2 and start the container using docker-compose

## EC2 Deployment
The final image is deployed to an AWS EC2 instance with Docker and Docker Compose pre-installed.

## Test Info
Tests written in app.test.js

Use supertest and jest

One endpoint tested

