# Yosys Docker Image

This repository provides a Docker setup to build, tag, and push a Docker image for [Yosys](http://www.clifford.at/yosys/), an open-source Verilog synthesis tool.

## Prerequisites

- Docker: Ensure Docker is installed on your system.

## Repository Structure

- `latest/`: Directory containing the Dockerfile for building the latest version of Yosys.
- `Makefile`: Script for building, tagging, and pushing the Docker image.

## Getting Started

### Clone the Repository

```sh
git clone https://github.com/m4j0rt0m/docker-yosys.git
cd docker-yosys
```

### Build and Push the Docker Image

To build and push the Docker image to Docker Hub, run:

```sh
make
```

This command will:
1. Build the Docker image.
2. Tag the Docker image.
3. Push the Docker image to Docker Hub.

### Makefile Targets

- `all`: Executes `build`, `tag`, and `push` sequentially.
- `build`: Builds the Docker image from the Dockerfile.
- `login`: Logs into Docker Hub.
- `tag`: Tags the Docker image with your Docker Hub username and version.
- `push`: Pushes the tagged Docker image to Docker Hub.
- `clean`: Removes the local Docker images.

## Detailed Usage

### Build the Docker Image

To build the Docker image manually, run:

```sh
make build
```

### Tag the Docker Image

To tag the Docker image, run:

```sh
make tag
```

### Push the Docker Image

To push the Docker image to Docker Hub, run:

```sh
make push
```

### Clean Up

To remove the local Docker images created during the build process, run:

```sh
make clean
```

## Configuration

The Makefile uses the following variables:
- `DOCKER_DIR`: Directory containing the Dockerfile (default: `latest`).
- `DOCKER_NAME`: Name of the Docker image (default: `yosys`).
- `DOCKER_VERSION`: Version tag for the Docker image (default: same as `DOCKER_DIR`).
- `DOCKER_HUB_USER`: Your Docker Hub username.

You can modify these variables directly in the Makefile or override them when running `make`:

```sh
make DOCKER_DIR=mydir DOCKER_NAME=myname DOCKER_VERSION=myversion DOCKER_HUB_USER=myuser
```

## Contributing

Contributions are welcome! Follow these steps to contribute:

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/fooBar`).
3. Commit your changes (`git commit -am 'Add some fooBar'`).
4. Push to the branch (`git push origin feature/fooBar`).
5. Create a new Pull Request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
