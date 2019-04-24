# mongodb-docker-server

MongoDB server boilerplate using Docker compose, with Mongo Express as management server

## How to start

Run `docker-compose up`.

## Server operations

### Get into the MongoDB server

- Run `docker exec -it mongo mongo`

### Create user

- Run `use admin` to select the admin DB.
- Run `db.auth('root', 'example')` to log on using the admin credential (root:example)
- Run create user command: `db.createUser( {user: "avinshum", pwd: "pwd", roles: [ { role: "readWrite", db: "db"}]})`. Note that the command restricts the new user to access the DB `db` only.

## Troubleshoot

### Volume management

#### Clean up container volume to start over

- It is useful if you have set a wrong admin password and want to start over. It usually happens at the early stage.

  Run `docker-compose rm -fv [SERVICE...]`

#### List volumes

- Run `docker volume ls`

#### Clean unused volumes

- Run `docker volume prune`

## Dockerhub Pages

- [MongoDB](https://hub.docker.com/_/mongo)
- [Mongo Express](https://hub.docker.com/_/mongo-express)
