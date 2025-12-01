# MEAN CRUD App — DevOps Deployment

**Stack:** MongoDB, Express, Angular, Node.js (MEAN)  
**DevOps:** Docker, Docker Compose, Nginx, AWS EC2, GitHub Actions (CI/CD)

## Project summary
A full-stack CRUD application built with the MEAN stack. The project is containerized using Docker with separate images for frontend and backend, uses MongoDB for persistence, and is configured to run via Docker Compose. Nginx is used as a reverse proxy to serve the Angular frontend and proxy API calls to the backend.

## What’s included
- `frontend/` — Angular app
- `backend/` — Node.js + Express API
- `Dockerfile` (backend and frontend) — multi-stage builds
- `docker-compose.yml` — service orchestration (mongo, backend, frontend, proxy)
- `nginx-static.conf` — Nginx reverse proxy config
- `README.md`, `.gitignore`, `LICENSE`

## Run locally with Docker (recommended)
1. Build & start:
```bash
docker compose up --build -d

