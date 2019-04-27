# Notes-App

A web application for writing and storing notes with Markdown support.

Current features:

- User sign-up
- User log-in
- Note creation
- Note modifcation
- Note deletion

Feature wishlist:

- [ ] Admin tooling
- [ ] Note sharing
- [ ] Note exporting

## Pre-requirements

Requires a PostgreSQL instance and a host with Python 3.7 or greater.

## Preparing for development

Follow these steps to start developing with this project:

1. Ensure `pip` and `pipenv` are installed
2. Clone repository: `git clone git@github.com:uqpu/notes-app`
3. `cd` into the repository
4. Activate virtualenv: `pipenv shell`
5. Install dependencies: `pipenv install`

## Using environment variables

The environment variables can be set by either using a `.env` file or by modifying the `config.py`. The `.env` file is the prefered method.

### Creating and using a .env file

1. Create the `.env` file in the project root directory

2. Add and modify as needed:

    ```sh
    export DB_USERNAME='demo'
    export DB_PASSWORD='password'
    export DB_HOST='127.0.0.1'
    export DB_NAME='notes'
    export DB_PORT='5432'
    export FLASK_ENV='development'
    export FLASK_APP='.'
    ```

3. If `pipenv install` was used to setup the enviroment, the `python-dotenv` package will automatically handle the variables. Otherwise execute `source .env` in the project root directory.

## Creating the database

From the PostgreSQL host, create the database: 

```sh
psql postgres -U demo -c "CREATE DATABASE notes;"
```

In this case, the user is `demo` and the database is `notes`

## Initializing the database

From the repository directory, perform the following:

1. Activate virtualenv: `pipenv shell`
2. Initalize database: `flask db init`
3. Migrate database: `flask db migrate`
4. Upgrade database: `flask db upgrade`

## Starting the application

From the repository directory, run:

```sh
flask run --host=0.0.0.0 --port=3000
```

The application can be exited by pressing CTRL+C.