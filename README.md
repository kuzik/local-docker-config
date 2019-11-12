# Installation
Install Docker and docker-compose (https://docs.docker.com/compose/install/)

Run `cp .env.example .env`

Set path to folder containing projects to `PROJECTS_PATH`

Run `docker-compose up`

For adding new site create new nginx config inside `nginx/sites` folder and restart nginx container.