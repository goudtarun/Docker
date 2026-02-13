# Docker Projects Repository

A collection of Docker projects demonstrating containerization of web applications, Python services, and database setups.

## Project Structure

This repository contains three main Docker projects:

### 1. **beginner** - Static Website with HTML/CSS
A beginner-friendly Docker project that containerizes a static HTML website (Christmas Piano template).

**Contents:**
- `Dockerfile` - Container configuration
- `index.html` - Main HTML file
- `templatemo_604_christmas_piano/` - Template assets including images and stylesheets
- `README.md` - Project-specific documentation

**Usage:**
```bash
cd beginner
docker build -t beginner-web .
docker run -p 80:80 beginner-web
```

Visit `http://localhost:80` to view the website.

---

### 2. **python-basic** - Python Application Container
A Python application running inside Docker, suitable for basic Python projects and scripts.

**Contents:**
- `Dockerfile` - Python environment configuration
- `app.py` - Main Python application
- `README.md` - Project-specific documentation

**Usage:**
```bash
cd python-basic
docker build -t python-basic .
docker run python-basic
```

---

### 3. **wp-db** - WordPress & Database Stack
A multi-container setup using Docker Compose for WordPress with MySQL database.

**Contents:**
- `docker-compose.yml` - Multi-container orchestration

**Services:**
- WordPress web server
- MySQL database

**Usage:**
```bash
cd wp-db
docker-compose up -d
```

Access WordPress at `http://localhost:8080`

---

## Getting Started

### Prerequisites
- Docker installed ([Download Docker](https://www.docker.com/products/docker-desktop))
- Docker Compose (included with Docker Desktop)
- Git

### Quick Start

1. **Clone the repository:**
```bash
git clone https://github.com/goudtarun/Docker.git
cd Docker
```

2. **Navigate to desired project:**
```bash
cd beginner
# or
cd python-basic
# or
cd wp-db
```

3. **Build and run the containers:**
```bash
# For single container projects
docker build -t project-name .
docker run project-name

# For multi-container projects (wp-db)
docker-compose up -d
```

---

## Requirements

- **Docker**: Version 20.10 or higher
- **Docker Compose**: Version 1.29 or higher (for wp-db)
- **RAM**: Minimum 2GB
- **Disk Space**: At least 5GB free space

---

## Common Commands

### Docker Commands
```bash
# Build an image
docker build -t image-name .

# Run a container
docker run -p host-port:container-port image-name

# List running containers
docker ps

# Stop a container
docker stop container-id

# Remove a container
docker rm container-id

# View logs
docker logs container-id
```

### Docker Compose Commands
```bash
# Start services
docker-compose up -d

# Stop services
docker-compose down

# View logs
docker-compose logs -f

# Rebuild services
docker-compose up -d --build
```

---

## 📝 Project Details

### beginner Project
- **Language:** HTML/CSS
- **Base Image:** nginx:latest
- **Port:** 80
- **Purpose:** Learn Docker basics with static web hosting

### python-basic Project
- **Language:** Python 3
- **Purpose:** Run Python applications in containers
- **Use Cases:** Scripts, APIs, data processing

### wp-db Project
- **Services:** WordPress + MySQL
- **Volumes:** Data persistence for database
- **Purpose:** Full-stack web application setup

---

## Troubleshooting

**Container won't start:**
```bash
# Check logs
docker logs container-name

# Rebuild the image
docker build --no-cache -t image-name .
```

**Port already in use:**
```bash
# Use a different port
docker run -p 8080:80 image-name
```

**Permission denied errors:**
```bash
# On Linux, run with sudo or add user to docker group
sudo usermod -aG docker $USER
```

---

## Resources

- [Docker Documentation](https://docs.docker.com/)
- [Docker Compose Documentation](https://docs.docker.com/compose/)
- [Dockerfile Best Practices](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)

---

## Author

**Tarun Goud**

- GitHub: [@goudtarun](https://github.com/goudtarun)
- Repository: [Docker Projects](https://github.com/goudtarun/Docker)

---

## License

This project is open source and available for educational purposes.

---

## Support

For issues or questions:
1. Check the project-specific README in each folder
2. Review the Troubleshooting section above
3. Open an issue on GitHub

---

**Last Updated:** February 2026
