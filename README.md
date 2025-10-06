# jenkins-nodejs-docker-demo

A **Mini DevOps Project** to demonstrate how to automate the build and deployment of a Node.js application using **Jenkins** and **Docker**.

## Project Overview

This project showcases a **CI/CD pipeline** built using **Jenkins**, which automatically:

        1. Pulls code from a GitHub repository

        2. Builds a Docker image of the Node.js app

        3. Runs the container automatically

        4. Verifies that the server is running successfully

Perfect for **Junior DevOps Engineers** who want hands-on experience with Jenkins pipelines and Docker integration.

## Project Structure
```
jenkins-nodejs-docker-demo/
│
├── Dockerfile        # Defines how the Node.js app is containerized
├── Jenkinsfile       # CI/CD pipeline script for Jenkins
├── package.json      # Node.js dependencies and start script
└── server.js         # Simple HTTP server
```

## Technologies Used

- **Jenkins** – CI/CD automation

- **Docker** – Containerization

- **Node.js** – Simple backend app

- **GitHub** – Source control

## How the Pipeline Works
| Stage                     | Description                                       |
| ------------------------- | ------------------------------------------------- |
| 🧩 **Checkout**           | Jenkins pulls the code from GitHub                |
| 🐳 **Build Docker Image** | Builds a Docker image from the Dockerfile         |
| 🧱 **Run Container**      | Runs the app in a Docker container                |
| 🔍 **Verify**             | Checks that the container is running successfully |

## How to Run Locally
```
# Clone the repository
git clone https://github.com/NahidCSERU/jenkins-nodejs-docker-demo.git
cd jenkins-nodejs-docker-demo

# Build Docker image
docker build -t jenkins-nodejs-docker-demo .

# Run container
docker run -d -p 3000:3000 --name nodejs-demo jenkins-nodejs-docker-demo

# Test in browser
http://localhost:3000
```
## Jenkins Setup Steps

1. Install **Jenkins** and **Docker** on your system

2. Ensure Jenkins has permission to run Docker commands

3. Create a **Pipeline job** in Jenkins

4. In the job configuration, select “Pipeline script from SCM”

5. Add your **GitHub repo URL**

6. Save and **Build Now**

## Webhook Integration (Optional)

To enable automatic builds on every code push:

- Go to your GitHub repo → **Settings → Webhooks**

- Add Jenkins URL → `/github-webhook/`

- Choose “Just the push event”

## Demo Video

[Watch Project Demo Here](https://youtu.be/5Ot-6PS233E)


## What I Learned

- How to connect **GitHub → Jenkins → Docker**

- How to write a **Declarative Jenkinsfile**

- How to debug “Cannot find module” errors inside containers

- How to manage container lifecycle from Jenkins pipeline

## Result

After the pipeline runs successfully, open your browser at:
```
http://<server-ip>:3000
```

You’ll see:

🚀 Hello from Jenkins + Docker + Node.js Mini Project! this is beasutiful

## Author
Nahid Hasan  
[Junior DevOps Engineer](https://www.linkedin.com/in/nahiddevops/)