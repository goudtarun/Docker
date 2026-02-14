# Nginx Reverse Proxy using Docker Compose 

##  Project Overview

This project demonstrates how to deploy multiple backend services using Docker Compose and configure Nginx as a reverse proxy.

The setup includes:

- App1 (Flask Application)
- App2 (Flask Application)
- Nginx (Reverse Proxy)

Nginx acts as a single entry point and routes traffic to different backend services based on the URL path.

---

##  Technologies Used

- Docker
- Docker Compose
- Nginx
- Python (Flask)

---

## Architecture
```
Browser
│
▼
Nginx (Port 80)
│
├── /app1 → app1 container (Port 5000)
└── /app2 → app2 container (Port 5000)
```



- Nginx listens on port 80
- Routes requests based on path
- Containers communicate through Docker internal network
- Docker provides automatic DNS resolution using service names

---

## Project Structure
```
nginx-reverseproxy/
│
├── app1/
│ ├── app.py
│ └── Dockerfile
│
├── app2/
│ ├── app.py
│ └── Dockerfile
│
├── nginx/
│ └── nginx.conf
│
└── docker-compose.yml
```



---

## 🔄 Nginx Configuration

Example `nginx.conf`:

```
nginx
events {}

http {
    server {
        listen 80;

        location /app1/ {
            proxy_pass http://app1:5000/;
        }

        location /app2/ {
            proxy_pass http://app2:5000/;
        }
    }
}
```

Build and Start Containers
```
docker compose up --build
```

## Access the Applications
```
http://<EC2-Public-IP>/app1
http://<EC2-Public-IP>/app2
```

Author

Tarun Goud
DevOps Learner | Docker & Cloud Enthusiast
