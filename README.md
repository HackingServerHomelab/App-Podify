# App-Podify

## First Time Prerequisites

1. `rm ./Data/postgres/.gitkeep`
2. Run [Traefik](https://github.com/HackingServerHomelab/App-Traefik)

## Running the Containers

1. Update the following volumes in [docker-compose.yml](./Docker/docker-compose.yml)
    * `../Data/podify:/storage`
    * `../Data/postgres:/var/lib/postgresql/data/pgdata`
2. Update the following environment vars in [docker-compose.yml](./Docker/docker-compose.yml)
    * `URL_HOST: https://podify.yourdomain.com`
    * `DATABASE_URL: postgres://podify:verysecurepassword@db/podify`
    * `SECRET_KEY_BASE: XXXXXXXXXXXXXXx...`
    * `INITIAL_USER_EMAIL: you@example.com`
    * `INITIAL_USER_PASSWORD: yourpassword`
    * `POSTGRES_USER: podify`
    * `POSTGRES_PASSWORD: verysecurepassword`
3. Update the Traefik host label in [docker-compose.yml](./Docker/docker-compose.yml)
    * ``"traefik.http.routers.podify-web.rule=Host(`localhost`)"``
4. Run `docker-compose -f ./Docker/docker-compose.yml up -d`

## First Time Setup

1. Visit <https://your-ip>
