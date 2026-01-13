# AI Coding Agent Instructions for JavaRepo

## Project Overview
JavaRepo is a minimal Express.js application exposing a single API endpoint. The project serves as a foundation for building REST APIs using Express.

**Stack:** Node.js with Express 5.x

## Architecture

### Core Components
- **[index.js](../index.js)**: Main application entry point
  - Initializes Express application
  - Defines a single GET endpoint at `/tshirt`
  - Configured to listen on PORT 8080

### Key Design Patterns
- **Inline routing**: All routes defined directly in index.js (suitable for minimal projects; refactor to separate router files when expanding)
- **Status-based responses**: Explicit HTTP 200 status codes and plain text responses

## Development Workflow

### Setup & Running
```bash
npm install                    # Install dependencies (Express)
node index.js                 # Start the server on localhost:8080
```

### Testing the API
```bash
curl http://localhost:8080/tshirt    # Returns "T-Shirt endpoint reached"
```

## Project Structure
```
.
├── index.js              # Application entry point
├── package.json          # Project metadata & dependencies
└── node_modules/         # Installed dependencies (Express & deps)
```

## Important Conventions

### Current Limitations & Expansion Points
- **No route versioning**: When adding routes, consider RESTful path structure (e.g., `/api/v1/tshirt`)
- **No error handling**: Implement proper error middleware when adding complexity
- **No test suite**: Scripts in package.json placeholder; add testing framework when needed

### When Expanding This Project
1. **Multiple routes**: Move to separate `routes/` directory with Express Router
2. **Middleware**: Add request logging, CORS, body parsing in the initialization phase
3. **Database**: If needed, configure connection pool in a separate `config/` module
4. **Environment variables**: Use `process.env` for PORT, DB credentials (currently hardcoded to 8080)

## External Dependencies
- **express@^5.2.1**: Web application framework with routing, middleware, response handling

## Development Notes
- Project uses standard npm scripts; no custom build tools configured
- No CI/CD pipeline, testing framework, or deployment configuration yet
