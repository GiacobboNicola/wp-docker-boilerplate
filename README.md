# wp-docker-boilerplate
This is a boilerplate to develop WordPress locally with an up-to-date stack. The main goal is to provide a simple and flexible solution to start a new project. It is based on [Aschmelyun's great repository](https://github.com/aschmelyun/docker-compose-wordpress).

## Requirements
- Docker
- Docker Compose
- Taskfile

## Stack
- Nginx: 1.25.2
- MariaDB: 11.5.2
- PHP: 8.2
- phpMyAdmin: 5.2.1
- WP-CLI: 2.11.0

## Installation
1. Clone the repository.
2. Enter the folder and run `task install-wp` to install WordPress in the `wordpress` folder.

## Usage
1. Run `task start` to start all the needed containers (*nginx*, *mariadb*, *php*, *phpmyadmin*). Use `task start -- -d` to run the containers in detached mode.
2. In a browser, navigate to `http://localhost:80` to access the WordPress. The user is `admin` and the password is `password`. You can change these credentials in the `.env` file (see the `sample.env` file as an example).
3. Run `task stop` to stop the all the containers or `task stop -- CONTAINER_NAME` to stop a specific container.

## Notes
1. If you face some permission issues with one of the folder generated when running docker compose (`wordpress` or `mariadb`), you can change the owner of those folder: `sudo chown -R $USER:$USER`.
2. Instead of generating a new WordPress installation you can simply copy and paste your own WordPress site in `wordpress` folder (a more detailed guide will be available soon).