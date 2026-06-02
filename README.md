AI Automation Web Deployment Project
A hands-on cloud infrastructure and DevOps project focused on containerizing an AI Automation application and deploying it securely onto public cloud infrastructure using AWS best practices.

🚀 Project Overview & Architecture
Containerization: Packaged cleanly using custom Dockerfiles to isolate dependencies.

Web Server & Reverse Proxy: Configured Nginx to handle public traffic routing and manage application uptime logs.

Cloud Hosting: Deployed on a managed AWS EC2 instance (Ubuntu CLI).

Cost Optimization: Infrastructure is managed responsibly and launched on-demand for active evaluations and technical interview rounds.

🛠️ Tech Stack & Tools Mastered
OS: Linux (Ubuntu) CLI

Cloud: AWS (EC2, VPC, Security Groups, IAM)

Containers: Docker (Dockerfiles, Image Management)

Web Serving: Nginx (Reverse Proxy)

Source Control: Git & GitHub

💻 Step-by-Step Deployment Logs
1. Pre-requisites & System Updates
Bash
sudo apt-get update && sudo apt-get upgrade -y
sudo apt-get install docker.io nginx -y
2. Verified Docker Container Deployment
Bash
# Building the custom AI app environment
docker build -t ai-automation-app .
docker run -d -p 5000:5000 --name running-app ai-automation-app
3. Nginx Reverse Proxy Mappings
Nginx
server {
    listen 80;
    server_name localhost;

    location / {
        proxy_pass http://127.0.0.1:5000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }
}
