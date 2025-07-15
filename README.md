## Overview

**greenlight** is a RESTful API project built as part of the "Let's Go Further" book. It demonstrates best practices in Go for building scalable, maintainable web services.

## Getting Started

### 1. Clone the Repository

```sh
git clone https://github.com/abhishek622/greenlight.git
cd greenlight
```

### 2. Set Up Environment Variables

Create a `.envrc` file in the project root with the following content:

```sh
export GREENLIGHT_DB_DSN="your_postgres_dsn_here"
```

Replace `your_postgres_dsn_here` with your actual PostgreSQL DSN.

> **Note:** If you use [direnv](https://direnv.net/), it will automatically load environment variables from `.envrc`.

### 3. Install Dependencies

```sh
go mod tidy
```

### 4. Run Database Migrations

Set up your database and run any required migrations.

### 5. Start the API Server

```sh
go run ./cmd/api
```

The server will start and listen for requests.

## API Documentation

### Healthcheck

- **GET `/v1/healthcheck`**  
   Returns API health status.

### Movies

- **POST `/v1/movies`**  
   Create a new movie. Requires `movies:read` permission.

- **GET `/v1/movies/:id`**  
   Retrieve details of a movie by ID. Requires `movies:write` permission.

- **PATCH `/v1/movies/:id`**  
   Update a movie by ID. Requires `movies:read` permission.

- **DELETE `/v1/movies/:id`**  
   Delete a movie by ID. Requires `movies:write` permission.

- **GET `/v1/movies`**  
   List all movies. Requires `movies:write` permission.

### Users

- **POST `/v1/users`**  
   Register a new user.

- **PUT `/v1/users/activated`**  
   Activate a user account.

- **PUT `/v1/users/password`**  
   Update a user's password.

### Tokens

- **POST `/v1/tokens/authentication`**  
   Create an authentication token.

- **POST `/v1/tokens/password-reset`**  
   Create a password reset token.

- **POST `/v1/tokens/activation`**  
   Create an activation token.

### Metrics

- **GET `/debug/vars`**  
   Exposes application metrics and variables.

## Note

This project is for learning purposes and follows the guidance from the "Let's Go Further" book.
