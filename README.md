# Tic-Tac-Toe

This repository contains the source code for a Dockerized Tic-Tac-Toe application. It includes Docker configurations for the server, client, and a terminal-based client interface. The project is structured to facilitate easy building, scanning for vulnerabilities, and pushing of Docker images using GitHub Actions.


## How to Play?

- Clone the Repository

```bash
git clone https://github.com/vladi2703/Tic-Tac-Toe.git
```

- On linux machine:

```bash
xhost +local:docker
docker compose up -d
```

- To stop:

```bash
docker compose down
```

---

## Screenshots

|            Player 1             |            Player 2             |
| :-----------------------------: | :-----------------------------: |
| ![Player 1](images/Player1.png) | ![Player 2](images/Player2.png) |

---

## Structure

- `server/`: Contains the Dockerfile and source code for the server component of the Tic-Tac-Toe game.
- `client/`: Contains the Dockerfile and source code for the client component.
- `client-terminal/`: Houses the Dockerfile and source code for a terminal-based client interface.
- `sql/`: Housed the SQL migrations for the players database.

Each component is containerized and managed independently.

## Prerequisites

- Docker

## CI/CD

**Using GitHub Actions for CI/CD**:

- The repository is configured with GitHub Actions for continuous integration and deployment.
- On every push to the master branch, Docker images are built, scanned for vulnerabilities, and pushed to Docker Hub.

## Contributing

Contributions to the Tic-Tac-Toe Dockerized application are welcome. Please read our [contributing guidelines](CODESTYLE.md) and submit pull requests to the repository.  

### Merging strategy

The strategy for merging in this project is "rebase and merge." This strategy offers several advantages:

1. Maintains a linear commit history

2. Preserves commit context

3. Enables easier bug tracking and reverting

Overall, the "rebase and merge" strategy helps maintain a clean and organized commit history, reduces merge conflicts, simplifies code reviews, and enables easier bug tracking and reverting.

**You have and idea for improvement? Open Github [issue](https://github.com/vladi2703/Tic-Tac-Toe/issues)!**


This project is licensed under the [MIT License](LICENSE).

- спомени защо пайплайна за докер се копи пействат джобовете - може и на стъпки, но при по-тежки контейнери ще е по-бавно

- add sql
- add sonar
- add snyk
  - added open source license check
- add docker-compose
- add kubernetes
- add s3
- add terraform
