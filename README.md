# Python FastAPI Starter API Project 🚀

Welcome to the **Python FastAPI Starter API Project**! This repository provides a scalable FastAPI project template designed for building production-ready APIs. With a focus on best practices, it incorporates async SQLAlchemy, PostgreSQL, and a repository pattern implementation. 

[![Releases](https://img.shields.io/github/release/YuenEye/python-fastapi-starter-api-project.svg)](https://github.com/YuenEye/python-fastapi-starter-api-project/releases)

## Table of Contents

- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [Directory Structure](#directory-structure)
- [API Endpoints](#api-endpoints)
- [Authentication](#authentication)
- [Error Handling](#error-handling)
- [Database Migrations](#database-migrations)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)

## Features

- **JWT Authentication**: Secure your API with JSON Web Tokens.
- **Comprehensive Error Handling**: Manage errors gracefully and provide clear feedback.
- **Modular Architecture**: Organize your code into modules for better maintainability.
- **Dependency Injection**: Simplify your code and enhance testability.
- **Pydantic Validation**: Ensure data integrity with automatic data validation.
- **Alembic Migrations**: Handle database schema changes easily.

## Technologies Used

This project utilizes the following technologies:

- **FastAPI**: A modern web framework for building APIs with Python 3.7+.
- **SQLAlchemy**: An ORM for Python that provides a full suite of well-known enterprise-level persistence patterns.
- **PostgreSQL**: A powerful, open-source object-relational database system.
- **Pydantic**: Data validation and settings management using Python type annotations.
- **Alembic**: A lightweight database migration tool for use with SQLAlchemy.

## Installation

To get started with this project, follow these steps:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/YuenEye/python-fastapi-starter-api-project.git
   cd python-fastapi-starter-api-project
   ```

2. **Create a virtual environment**:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install the dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up the environment variables**: Create a `.env` file in the root directory and add your PostgreSQL database URL and JWT secret key. For example:
   ```env
   DATABASE_URL=postgresql://user:password@localhost/dbname
   JWT_SECRET_KEY=your_jwt_secret_key
   ```

5. **Run the database migrations**:
   ```bash
   alembic upgrade head
   ```

6. **Start the application**:
   ```bash
   uvicorn app.main:app --reload
   ```

Now, your FastAPI application should be running at `http://127.0.0.1:8000`.

## Usage

Once the application is running, you can access the interactive API documentation at `http://127.0.0.1:8000/docs`. Here, you can test the endpoints and see the responses.

## Directory Structure

The project follows a modular structure for better organization:

```
python-fastapi-starter-api-project/
├── app/
│   ├── api/
│   │   ├── v1/
│   │   │   ├── endpoints/
│   │   │   └── api.py
│   │   └── dependencies.py
│   ├── core/
│   │   ├── config.py
│   │   └── security.py
│   ├── db/
│   │   ├── base.py
│   │   ├── models.py
│   │   └── session.py
│   ├── main.py
│   ├── schemas/
│   └── services/
├── alembic/
├── tests/
└── requirements.txt
```

## API Endpoints

The API includes various endpoints. Here are some examples:

### User Endpoints

- **Create User**: `POST /api/v1/users/`
- **Get User**: `GET /api/v1/users/{user_id}`
- **Update User**: `PUT /api/v1/users/{user_id}`
- **Delete User**: `DELETE /api/v1/users/{user_id}`

### Authentication Endpoints

- **Login**: `POST /api/v1/auth/login`
- **Logout**: `POST /api/v1/auth/logout`

## Authentication

This project uses JWT for authentication. Upon successful login, the server returns a JWT token. You must include this token in the `Authorization` header for protected routes.

Example of the `Authorization` header:
```
Authorization: Bearer <your_token>
```

## Error Handling

The application includes comprehensive error handling. Common HTTP errors are caught and returned in a consistent format. For example:

- **404 Not Found**: When a resource does not exist.
- **401 Unauthorized**: When authentication fails.
- **422 Unprocessable Entity**: When validation fails.

## Database Migrations

Alembic handles database migrations. To create a new migration, run:
```bash
alembic revision --autogenerate -m "your_message"
```
To apply the migration, use:
```bash
alembic upgrade head
```

## Testing

Testing is essential for maintaining code quality. This project includes a `tests` directory with unit tests for various components. To run the tests, execute:
```bash
pytest tests/
```

## Contributing

Contributions are welcome! If you have suggestions for improvements or find bugs, please open an issue or submit a pull request.

1. Fork the repository.
2. Create your feature branch (`git checkout -b feature/YourFeature`).
3. Commit your changes (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Open a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

For the latest releases, visit [Releases](https://github.com/YuenEye/python-fastapi-starter-api-project/releases). 

You can download and execute the latest version from the releases section.