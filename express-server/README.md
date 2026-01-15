# Express Server

This project is a simple Express server that listens on port 8001. It is set up to automatically restart using Nodemon when changes are made to the source files.

## Project Structure

```
express-server
├── src
│   └── index.js        # Entry point of the application
├── package.json        # Configuration file for npm
├── nodemon.json        # Configuration for Nodemon
├── Dockerfile          # Instructions for building the Docker image
└── README.md           # Documentation for the project
```

## Setup Instructions

1. **Clone the repository:**
   ```
   git clone https://github.com/Wilcolab/Anythink-Market-dpejzox0.git
   cd Anythink-Market-dpejzox0/express-server
   ```

2. **Install dependencies:**
   ```
   yarn install
   ```

3. **Start the server:**
   ```
   yarn start
   ```

The server will be running on `http://localhost:8001`.

## Usage

This server currently does not define any endpoints. You can extend it by adding routes in the `src/index.js` file.

## Docker

To build and run the Docker container, use the following commands:

1. **Build the Docker image:**
   ```
   docker build -t express-server .
   ```

2. **Run the Docker container:**
   ```
   docker run -p 8001:8001 express-server
   ```

The server will be accessible at `http://localhost:8001` from your host machine.

## Port Configuration

The Node.js Express server is configured to run on **port 8001**. This is defined in `src/index.js`:

```javascript
const PORT = 8001;
```

When running the server (either locally or via Docker), it will listen on port 8001 and be accessible at `http://localhost:8001`.