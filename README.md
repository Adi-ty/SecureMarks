# SecureMarks

### A NestJS API for Secure Bookmarking

SecureMarks is a RESTful API that allows users to manage bookmarks with secure authentication. It is built with NestJS and uses E2E testing to ensure reliable functionality.

## Project Setup

- Clone the repo

```
bash

git clone https://github.com/Adi-ty/SecureMarks.git
cd SecureMarks
```

- Install dependencies

```
yarn install
```

- DB setup

  - Make a .env and .env.test file for setting up development and test db.
  - Add DATABASE_URL and JWT_SECRET in the .env and .env.test.
  - To launh your database

  ```
  docker compose up dev-db -d
  ```

- Restarting db

```
yarn db:dev:restart
```

- Running the app

```
shell

# development
$ yarn run start

# watch mode
$ yarn run start:dev

# production mode
$ yarn run start:prod

```

- To run all the e2e tests

```


# e2e tests
$ yarn run test:e2e


```

## Getting Started

To use SecureMarks, you must first sign up for an account. To do so, send a POST request to the `auth/signup` route with your desired `email` and `password` .
This will return an access token, which you should save for future requests. To access other routes, send a GET request to the desired route with the access token in the `Authorization` header:

## Routes

Currently only following routes are available in SecureMarks:

### Authentication

- `POST /auth/singup`

Creates new user with provided email id and password

Request body:

```
{
  "email": "test@email.com",
  "password": "abcdef"
}
```

- `POST /auth/singin`
  Authenticates a user and returns an access token

Request body:

```
{
  "email": "test@email.com",
  "password": "1234"
}

```

### User

- `GET /users/me`
  Returns the authenticated users information
- `PATCH /users/:id`
  Updates the authenticated user's information.
  Request body:

```
{
  "firstName": "Adi",
  "email": "test1@email.com"
}
```

### Bookmark
