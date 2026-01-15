# Anythink Market

This project contains two backend servers for managing tasks: a Python FastAPI server and a Node.js Express server.

## Servers

| Server | Technology | Port |
|--------|------------|------|
| Python Server | FastAPI | 8000 |
| **Node Server** | **Express.js** | **8001** |

---

## Node.js Express Server

The Express server is located in the `express-server/` directory and **runs on port 8001**.

### Project Structure

- `express-server/src/index.js`: Main server file with API endpoints
- `express-server/package.json`: Node.js dependencies and scripts
- `express-server/Dockerfile`: Docker configuration for the Express server

### Getting Started

#### Local Development
```bash
cd express-server
yarn install
yarn start
```

The Node server will be running at `http://localhost:8001`.

#### Using Docker
```bash
docker compose up
```

### API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/` | Returns "Hello World" message |
| GET | `/tasks` | Retrieves all tasks as JSON |
| POST | `/tasks` | Adds a new task to the list |

#### Examples

```bash
# Test root endpoint
curl http://localhost:8001/

# Get all tasks
curl http://localhost:8001/tasks

# Add a new task
curl -X POST http://localhost:8001/tasks \
  -H "Content-Type: application/json" \
  -d '{"text":"Your task here"}'
```

---

## Python FastAPI Server

The FastAPI server is located in the `python-server/` directory and runs on port 8000.

### Project Structure

- `python-server/src/main.py`: FastAPI server implementation with task routes
- `python-server/src/__init__.py`: Python package marker
- `python-server/requirements.txt`: Python dependencies
- `python-server/Dockerfile`: Docker configuration for the FastAPI server

### Getting Started

```bash
docker compose up
```

The Python server will be running at `http://localhost:8000`.

### API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/tasks` | Adds a task to the task list |
| GET | `/tasks` | Retrieves the task list |

---

## Docker Compose

The `docker-compose.yml` file defines both services. To run all servers:

```bash
docker compose up
```

This will start:
- **Node Express server** on port **8001**
- Python FastAPI server on port 8000
