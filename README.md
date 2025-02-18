# Three-Tier Dockerized Application

Three-Tier Dockerized Application follows Docker best practices, using a multi-stage build for the backend, a database with host-stored credentials, and an NGINX reverse proxy for HTTPS. Each component runs in its own container, and the entire system is managed with Docker Compose, allowing easy deployment and teardown with a single command. 🚀

---

## Project Structure

```
project/
│── backend/          # Backend application files
│── conf/             # Nginx configuration files
│── db.env            # Database credentials (stored on host)
│── docker-compose.yml # Docker Compose file to manage services
│── nginx-certs/      # SSL certificates for HTTPS
```

---

## Prerequisites

- **Docker** & **Docker Compose** installed  
- Ensure `db.env` and `nginx-certs/` exist in the project directory  

---

## Setup & Run the Application

### 1. Build the Backend Image
Navigate to the backend directory and build the image:  

```bash
cd backend/
docker build -t go-app .
```

### 2. Start All Services

Run the following command from the **project root directory** to start all services:

```bash
docker compose up -d
```

### 3. Access the Application

Once the containers are running, open your browser and visit:

```bash
https://localhost
```

If you are connecting via **SSH**, use the machine’s IP instead:

```bash
https://<your-server-ip>
```

## Shutting Down the Application

To stop all containers, run:

```bash
docker compose down
```



