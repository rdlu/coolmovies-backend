# CoolMovies

A simple graphql service using PostGraphile to provide CoolMovies Reviews.

It's also intented to be used as part of frontend challenges with GraphQL.

## Requirements

- Docker, a recent version (>= 20)
- Docker Compose (one compatible with above docker)
- Your local ports 5432 and 5000 free (not running another postgres server, for instance)

You need docker and docker compose installed on your machine. It supports Linux, MacOS and Windows.

If it's your first time, you can follow the official instructions:
https://docs.docker.com/desktop/
https://docs.docker.com/compose/install/

## Running the server

    git clone https://github.com/rdlu/coolmovies-backend.git
    cd coolmovies-backend
    docker-compose up

Wait for a log message like this: `PostGraphile v4.12.3 server listening on port 5000`

Not try to connect to GraphiQL: http://localhost:5000/graphiql


## Basic CRUD Operations

You can use all available here:
https://www.graphile.org/postgraphile/crud-mutations/

Also you can use GraphiQL Explorer by accessing your local server:
http://localhost:5000/graphiql

## Reinitializing the database with seed data

Go to your project directory using your preferred terminal, then

    docker-compose down
    docker volume rm coolmovies-backend_db
    docker rmi coolmovies-db:latest
    docker-compose up

If you want also to rebuild the Postgraphile Server, run this before the `up` command.

    docker rmi coolmovies-graphql:latest
    