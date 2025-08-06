# Inception

This project sets up a complete Docker infrastructure, orchestrated with `docker-compose`, to host multiple web services and databases. It is a DevOps exercise aimed at automating the deployment of complex environments.

## Project Architecture

The architecture is based on several Docker containers, each isolating a specific service. Services are defined in `srcs/docker-compose.yml` and organized in dedicated folders under `srcs/requirements/`.

### Main Services

- **nginx**: Web server acting as a reverse proxy.
- **mariadb**: Relational database.
- **wordpress**: WordPress CMS connected to MariaDB.

## Installation and Usage

1. **Clone the repository**
   ```zsh
   git clone <repo_url>
   cd Inception
   ```

2. **Configure environment variables**
   - Adapt configuration files if needed in `srcs/requirements/*/conf` or `tools`.

3. **Launch the infrastructure**
   - With the Makefile:
     ```zsh
     make
     ```

4. **Stop and clean up**
   ```zsh
   make down
   # or
   docker-compose -f srcs/docker-compose.yml down
   ```

## Folder Structure

- `srcs/docker-compose.yml`: Service and network definitions.
- `srcs/requirements/`: Folders for each service with their Dockerfile and configuration.
- `build-run.sh`: Script to build and launch containers.
- `Makefile`: Simplified commands to build, launch, stop and clean up.

## Authors

- mkaliszc
