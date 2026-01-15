# Express Server

A Node.js Express server that provides a RESTful API for managing tasks. The server listens on port 8001 and is configured with Nodemon for automatic restart during development.

## Project Structure

```
express-server
├── src
│   └── index.js        # Entry point of the application
├── package.json        # Configuration file for npm dependencies
├── nodemon.json        # Configuration for Nodemon auto-reload
├── Dockerfile          # Instructions for building the Docker image
└── README.md           # Documentation for the project
```

## Prerequisites

- **Node.js**: Version 14 or higher
- **npm** or **yarn**: Package manager for installing dependencies
- **Docker** (optional): For containerized deployment

## Dependencies

This project uses the following npm packages:

- **express** (^4.17.1): Fast, unopinionated web framework for Node.js
- **nodemon** (^2.0.7): Development tool that automatically restarts the server on file changes

## Environment Setup

### Local Development

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Wilcolab/Anythink-Market-dpejzox0.git
   cd Anythink-Market-dpejzox0/express-server
   ```

2. **Install dependencies:**
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Start the development server:**
   ```bash
   npm start
   # or
   yarn start
   ```

The server will start on `http://localhost:8001` with hot-reload enabled.

### Using Docker

Run the server using Docker Compose (from the project root directory):

```bash
cd ..
docker compose up
```

Or build and run the Docker container individually:

1. **Build the Docker image:**
   ```bash
   docker build -t express-server .
   ```

2. **Run the Docker container:**
   ```bash
   docker run -p 8001:8001 express-server
   ```

The server will be accessible at `http://localhost:8001`.

## API Endpoints

### GET /
Returns a simple "Hello World" message.

**Response:**
```
Hello World
```

### GET /tasks
Retrieves all tasks.

**Response:**
```json
{
  "tasks": [
    "Write a diary entry from the future",
    "Create a time machine from a cardboard box",
    "Plan a trip to the dinosaurs",
    "Draw a futuristic city",
    "List items to bring on a time-travel adventure"
  ]
}
```

### POST /tasks
Adds a new task to the list.

**Request Body:**
```json
{
  "text": "Your new task here"
}
```

**Success Response (200):**
```json
{
  "message": "Task added successfully"
}
```

**Error Response (400):**
```json
{
  "error": "Task text is required and must be a non-empty string"
}
```

## Development

### Hot Reload

The server uses Nodemon to watch for file changes in the `src/` directory. Any changes to `.js` files will automatically restart the server.

Configuration is in `nodemon.json`:
```json
{
  "watch": ["src"],
  "ext": "js",
  "exec": "node src/index.js"
}
```

### Adding New Endpoints

To add new endpoints, edit `src/index.js`:

```javascript
app.get('/your-endpoint', (req, res) => {
  res.json({ message: 'Your response' });
});
```

## Port Configuration

The server runs on port **8001** by default. This is configured in `src/index.js`:

```javascript
const PORT = 8001;
```

## Troubleshooting

- **Port already in use**: Ensure port 8001 is not being used by another application
- **Module not found**: Run `npm install` or `yarn install` to install dependencies
- **Docker container exits immediately**: Check logs with `docker logs <container-name>`