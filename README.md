# hoppscotch-docker-compose
A docker compose build from community hoppscotch.com build.


## Objective

Running container with Docker compose

Extension of https://github.com/hoppscotch/hoppscotch 

## Containers

- Hoppscotch Frontend
- Hoppscotch Backend
- Hoppscotch Admin
- PostgreSQL
- Ngnix


## Setup 
- Configure and update default.env with valid values
- command: `docker compose up --build`
- This should spin up all containers

#### Important Note for database migration
You need to create database and run migrations before the backend serive is up, else the backend server will not run.

Steps:
1. You need to create database `hoppscotch` in the PostgreSQL server.
2. In `compose.yml`Comment line no. 15  and uncomment line no. 22
3. run command: `docker compose up --build` this should run the migrations.
4. restore back the `compose.yml` to its original state.
5. re-run step (3)


### Usage
- Once server all containers are running successfully you should be able to access the services as follows:
- Frontend: `http://localhost`
- Backend: `http://backend.localhost`
- Admin: `http://admin.localhost`

The above is configured in `./nginx/default.conf`, for development/production containers please updated the same for actual domain name.
Example: `localhost` will be replaced by `example.com`


Feel free to make changes to `compose.yml` or other configurations as per your requirements.


## Hoppscotch setup and installation guide

https://docs.hoppscotch.io/documentation/self-host/community-edition/install-and-build