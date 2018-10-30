# Dockerize-Orb
A [CircleCI](https://circleci.com/) orb for [Dockerize](https://github.com/jwilder/dockerize)

Wait for services to come online before progressing to the next step of your config.

Example:

```
version: 2.1
orbs:
  dockerize: sandbox/dockerize@dev:0.0.1

jobs:
  build:
    docker: 
      - image: circleci/node
      - image: circleci/postgres
    steps:
      - dockerize/wait:
          service: postgres #or enter `tcp://127.0.0.1:5432`
```

## Parameters
Version:
   -  Specify Dockerize version. Default is '0.6.1'
 
Service:
  - Specify the URL for the database or simply enter the name of the service. Check readme for default supported services.


Timeout:
  - Optionally set timeout in seconds. (default 60)

## Services

Rather than entering the full connection string manually (ex: `tcp://127.0.0.1:5432`), these services can be entered by name.

- MongoDB
- MySQL
- Postgres

Please feel free to suggest others.
