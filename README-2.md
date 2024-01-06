# Tic-Tac-Toe Dockerized Application

This repository contains the source code for a Dockerized Tic-Tac-Toe application. It includes Docker configurations for the server, client, and a terminal-based client interface. The project is structured to facilitate easy building, scanning for vulnerabilities, and pushing of Docker images using GitHub Actions.

## Structure

- `server/`: Contains the Dockerfile and source code for the server component of the Tic-Tac-Toe game.
- `client/`: Contains the Dockerfile and source code for the client component.
- `client-terminal/`: Houses the Dockerfile and source code for a terminal-based client interface.

Each component is containerized and managed independently.

## Prerequisites

- Docker
- GitHub Account (for using GitHub Actions)
- Docker Hub Account (for storing Docker images)

## Setup and Usage

1. **Clone the Repository**:

2. **Building the Docker Images**:

- You can build the Docker images locally by running:

  ```bash
  docker build -f server/Dockerfile -t [your-dockerhub-username]/tic-tac-toe:server .
  docker build -f client/Dockerfile -t [your-dockerhub-username]/tic-tac-toe:client .
  docker build -f client-terminal/Dockerfile -t [your-dockerhub-username]/tic-tac-toe:client-terminal .
  ```

3. **Running the Application**:

- To run the server:

  ```bash
  docker run -dp 8080:8080 [your-dockerhub-username]/tic-tac-toe:server
  ```

- To run the client or client-terminal:

  ```bash
  docker run -it [your-dockerhub-username]/tic-tac-toe:client
  docker run -it [your-dockerhub-username]/tic-tac-toe:client-terminal
  ```

4. **Using GitHub Actions for CI/CD**:

- The repository is configured with GitHub Actions for continuous integration and deployment.
- On every push to the master branch, Docker images are built, scanned for vulnerabilities, and pushed to Docker Hub.

## Contributing

Contributions to the Tic-Tac-Toe Dockerized application are welcome. Please read our contributing guidelines and submit pull requests to the repository.

## License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgements

- Special thanks to [GitHub Actions](https://github.com/features/actions) and [Trivy](https://github.com/aquasecurity/trivy) for CI/CD and security scanning tools.
