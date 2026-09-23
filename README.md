# Multi-Container App V2 🚀

A simple multi-container web application built with **Docker, Nginx, and Python Flask**.

## Architecture

- **Frontend:** HTML + Nginx
- **Backend:** Python Flask
- **Containerization:** Docker
- **Networking:** Docker custom network

## Project Structure

```text
multi-app-v2/
├── frontend/
│   ├── index.html
│   └── Dockerfile
│
└── backend/
    ├── app.py
    ├── requirements.txt
    └── Dockerfile
```

## How It Works

The frontend runs inside an Nginx container.

The backend runs inside a Python Flask container.

Both containers communicate through a custom Docker network called `v2-network`.

## Ports

| Service | Host Port | Container Port |
|---|---:|---:|
| Frontend | 8081 | 80 |
| Backend | 5001 | 5000 |

## Run

### Backend

```bash
cd backend
sudo docker build -t v2-backend .
sudo docker run -d --name v2-backend -p 5001:5000 --network v2-network v2-backend
```

### Frontend

```bash
cd frontend
sudo docker build -t v2-frontend .
sudo docker run -d --name v2-frontend -p 8081:80 --network v2-network v2-frontend
```

Open the application:

```text
http://localhost:8081
```

## Technologies

- Linux
- Git & GitHub
- Docker
- Nginx
- Python
- Flask
- Docker Networking
