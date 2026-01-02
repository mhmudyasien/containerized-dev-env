# containerized-dev-env

# Project Name

> A DevOps-optimized container setup using Docker and Docker Compose for reproducible, secure, and efficient local development and CI workflows.

---

## ✨ Why This Docker Setup?

### 🐳 Optimized `Dockerfile`
- **Multi-stage build**: Keeps the final image small by discarding build-time dependencies.
- **Runs as non-root**: Enhances security by using a dedicated, unprivileged user.
- **Leverages layer caching**: Installs dependencies before copying source code to speed up iterative builds.
- **Minimal base image**: Uses a slim or distroless base to reduce vulnerabilities and image size.
- **Includes `.dockerignore`**: Prevents unnecessary files (like `.git`, `__pycache__`, etc.) from bloating the build context.

### 🧩 Declarative Orchestration with `docker-compose.yml`
- **One-command environment**: `docker compose up` starts everything needed for local development.
- **Hot-reloading support**: Optional dev override (`docker-compose.dev.yml`) mounts source code for live updates.
- **Isolated networking**: Services communicate over a private Docker network with DNS-based service discovery.
- **Configuration via environment**: Uses `.env` files for easy, safe configuration without hardcoding secrets.

---

## 🚀 Quick Start

### Prerequisites
- Docker Engine ≥ 20.10  
- Docker Compose ≥ v2.0 (bundled with Docker Desktop or installed separately)

### Build & Run
```bash
# Build the application image
docker compose build

# Start services in the background
docker compose up -d

# View real-time logs
docker compose logs -f
