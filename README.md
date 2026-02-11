# Docker
This Repo Represents all the docker projects i.e (beginner, Intermediate and Advanced)


# Dockerized Static Website using Nginx

This project demonstrates how to containerize a static website template using Docker and Nginx.

## Project Structure

.
├── Dockerfile
├── templatemo-604-christmas-piano/
│   ├── index.html
│   ├── css/
│   ├── js/
│   └── images/
└── README.md

## Dockerfile Used

```FROM ubuntu```
```RUN apt update &&```
```RUN apt install nginx -y```
```COPY templatemo-604-christmas-piano/ /usr/share/nginx/html/```
```CMD ["nginx" , "-g" , "daemon-off;"]```

## Build the Docker Image

docker build -t docker-static-site .

## Run the Container

docker run -d -p 80:80 --name static-site docker-static-site

Then open:

http://<your-server-public-ip>

## Technologies Used

- Docker
- Nginx
- HTML / CSS / JS
- Linux (Ubuntu)

## Author

Tarun Goud
