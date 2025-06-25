# Hello World CI/CD Deployment 

This project demonstrates a **production-grade Continuous Integration and Continuous Deployment (CI/CD) pipeline** for a simple Node.js "Hello World" app, deployed automatically to an AWS EC2 instance using **GitLab CI/CD**, **Docker**, and **Docker Compose**.

While the app itself is minimal, the focus of this project is to highlight **DevOps best practices**, automation, and infrastructure reliability.

---

## Project Highlights

- **CI/CD Pipeline** using GitLab
- **Automated Docker image build & push**
- **SSH-based deployment to AWS EC2**
- **Docker Compose orchestration**
- **Best practices**: secure credentials, caching, rollback support, deployment stability

---

## Technologies Used

| Stack Component      | Tool / Service                     |
|----------------------|------------------------------------|
| App Framework        | Node.js + Express                  |
| Version Control      | Git + GitLab + GitHub              |
| Containerization     | Docker, Docker Compose             |
| CI/CD                | GitLab CI/CD                       |
| Deployment Platform  | AWS EC2 (Ubuntu)                   |
| Testing              | Jest + Supertest                   |

---

## CI/CD Pipeline Structure

The `.gitlab-ci.yml` file defines the following pipeline stages:

1. **Build**
   - Docker image is built and pushed to GitLab Container Registry.
   - Uses `docker:dind` for isolated builds.
   - Node modules cached for faster builds.

2. **Test**
   - Runs automated tests using `jest` inside a `node:18` container.
   - Uses `npm ci` and a reliable registry mirror for stability.

3. **Deploy**
   - Secure SSH deployment to EC2 instance.
   - Transfers `docker-compose.yml` and restarts containers.

---


## How to Run Locally

### 1. Clone the repo
git clone https://github.com/Hamidhrf/hello-world-ci-cd.git
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

## DevOps Best Practices Implemented
✅ Custom EC2 GitLab Runner for isolation and performance

✅ Environment variables securely stored in GitLab

✅ SSH key-based deployment

✅ npm mirror and retries for stability

✅ Pipeline caching for faster builds

✅ Manual rollback strategy with versioned images


