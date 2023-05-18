# Kafka-Flask Coding Challenge

This repository contains the base code to complete the Kafka-Flask Coding Challenge.

## Before you start

Make sure you complete the following steps before you start working on the challenge:
- [ ] Have Python 3.9 or higher installed. We recommend using [pyenv](https://github.com/pyenv/pyenv).
- [ ] Have installed Poetry. Visit the [poetry](https://python-poetry.org/docs/) website for more info.
- [ ] Have docker and docker-compose installed (you can also use cloud resources, but that's on you).
- [ ] Clone this repository and install the dependencies using `poetry install`.
  - **Do this before the interview so you don't have to wait for the dependencies to install or lose time with environment setup.**

## Getting started

Follow the steps below to get started with the challenge:
1. We're using alembic to manage migrations. Run the initial migrations using `poetry run alembic upgrade head`.
    1. You'll have to setup your database connection string in the `alembic.ini` file.
2. Start your flask server using `poetry run flask run`.
3. Create a topic in the Kafka cluster: `docker exec broker kafka-topics --bootstrap-server broker:9092 --create --topic TOPIC`

Getting/setting Kafka configs are on you.

Follow the Challenge instructions in the [challenge](https://docs.google.com/document/d/1idGbY52tQ9v_RdF8U_yEQwt_Eg9ldqZoEigryT2eDMA) file.

## Folder structure:

- `alembic`: Contains the alembic configuration and migrations.
- `api`: Contains the flask apps.
- `tests`: Contains the tests.

We've installed flask-openapi3, which will generate an OpenAPI 3 specification for you. You can find it at `/openapi`. 

This library also makes it slightly different to develop your API, making Flask flavor a little more like FastAPI 
(eg.: instead of router.route, you use router.get/post/put, etc). It also uses pydantic for schema definition.
You can read more about it [here](https://luolingchun.github.io/flask-openapi3/v2.x/Quickstart/).

## Running tests

We're using pytest to run tests. You can run the tests by running `poetry run pytest`.

We've already provided you with some boilerplate to run database tests. You can find them in the `tests` folder.