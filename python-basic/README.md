# Dockerized Python Flask Application 🚀

##  Project Overview

This project demonstrates how to containerize a simple Python Flask web application using Docker.

The application runs inside a Docker container and is accessible via a mapped host port.


## Technologies Used

- Python 3
- Flask
- Docker


## Project Structure

```
docker-python-app/
│
├── app.py
├── requirements.txt
├── Dockerfile
└── README.md
```

## Dockerfile Explainantion
```
- **FROM** → Base image (Python runtime)
- **WORKDIR** → Sets working directory inside container
- **COPY** → Copies application files into container
- **RUN** → Installs dependencies
- **EXPOSE** → Documents container port
- **CMD** → Starts the Flask application
```

## Dockerfile Used
```
FROM    ubuntu
RUN     apt update
RUN     apt install python3 python3-pip -y
RUN     apt install python3-flask -y
WORKDIR /app
EXPOSE  5000
COPY    app.py .
CMD     ["python3", "app.py"]
```

## Build the Docker Image
```
docker image build . -t python3:v1
```

## Run the container
```
docker container run -d -p 5000:5000 --name python-app python3:v1
```

## To verify
```
http://x.x.x.x:5000  
```




## Author

Tarun Goud
