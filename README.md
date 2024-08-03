# URL Shortener with Golang and Redis

This project is a URL shortener service built using Golang with the Fiber web framework and Redis for storage. The service provides endpoints for shortening URLs and resolving shortened URLs.

## Features

- **Shorten URLs:** Post a URL to create a shortened version.
- **Resolve Shortened URLs:** Redirect from a shortened URL to the original URL.
- **Rate Limiting:** Limits the number of requests a user can make to prevent abuse.
- **Expiry:** Set an expiry time for shortened URLs.
- **HTTPS Enforced:** Automatically convert URLs to HTTPS.

## Project Structure

- **`main.go`**: The entry point of the application. Sets up routes and initializes the Fiber application.
- **`routes/resolve.go`**: Contains the logic for resolving shortened URLs.
- **`routes/shorten.go`**: Contains the logic for shortening URLs.
- **`Dockerfile`**: Defines the Docker image for the API service.
- **`Dockerfile.redis`**: Defines the Docker image for the Redis service.
- **`docker-compose.yml`**: Defines the services (API and Redis) for Docker Compose.

## Getting Started

### Prerequisites

- Docker
- Docker Compose

### Running the Application

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/url-shortener-GO-Redis.git
    cd url-shortener-GO-Redis
    ```

2. Build and run the application with Docker Compose:

    ```bash
    docker-compose up --build
    ```

   This command builds the Docker images and starts the containers for both the API and Redis services.

3. The API service will be accessible at `http://localhost:3000`.

### Environment Variables

The application uses environment variables for configuration. Create a `.env` file in the root directory with the following variables:

```env
APP_PORT=3000
API_QUOTA=10
DOMAIN=http://localhost:3000