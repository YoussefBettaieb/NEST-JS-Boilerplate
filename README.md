# NestJS Backend API Boilerplate

<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="120" alt="Nest Logo" /></a>
</p>

A production-ready boilerplate for building scalable and maintainable backend APIs using [NestJS](https://nestjs.com/), TypeScript, and PostgreSQL.

## Features

- **NestJS Framework** - Progressive Node.js framework for building efficient server-side applications
- **TypeScript** - Full TypeScript support for type safety
- **PostgreSQL Integration** - ORM integration with TypeORM for database operations
- **Authentication** - JWT-based authentication with guards and strategies
- **Authorization** - Role-based access control with admin guards
- **User Management** - Pre-built user module with CRUD operations
- **Structured Architecture** - Organized module structure with controllers, services, and DTOs
- **Testing Ready** - Jest configuration for unit and e2e tests
- **Development Tools** - ESLint configuration and hot-reload support

## Project Structure

```
src/
├── app.controller.ts          # Main application controller
├── app.module.ts              # Root module
├── app.service.ts             # Application service
├── main.ts                    # Application entry point
├── auth/                      # Authentication module
│   ├── auth.service.ts
│   ├── auth.controller.ts
│   ├── jwt-auth.guard.ts
│   ├── jwt.strategy.ts
│   └── dtos/
│       ├── login.dto.ts
│       └── register.dto.ts
├── users/                     # Users module
│   ├── users.service.ts
│   ├── users.controller.ts
│   ├── user.entity.ts
│   └── dtos/
│       └── update-user.dto.ts
└── guards/                    # Custom guards
    └── admin.guard.ts
```

## Prerequisites

- Node.js (v16+)
- npm or yarn
- PostgreSQL database

## Getting Started

### Installation

1. Clone the repository and install dependencies:

```bash
npm install
```

2. Install PostgreSQL driver:

```bash
npm install pg @types/pg
```

3. Set up environment variables by creating a `.env` file in the root directory:

```env
DATABASE_HOST=localhost
DATABASE_PORT=5432
DATABASE_USER=postgres
DATABASE_PASSWORD=your_password
DATABASE_NAME=nest_boilerplate
JWT_SECRET=your_jwt_secret_key
```

### Running the Application

```bash
# Development (with hot-reload)
npm run start:dev

# Production
npm run start:prod

# Watch mode
npm run start
```

The API will be available at `http://localhost:3000`

## Testing

```bash
# Unit tests
npm run test

# E2E tests
npm run test:e2e

# Test coverage
npm run test:cov
```

## Available Endpoints

### Authentication

- `POST /auth/register` - Register a new user
- `POST /auth/login` - Login and receive JWT token

### Users

- `GET /users` - Get all users (admin only)
- `GET /users/:id` - Get user by ID
- `PATCH /users/:id` - Update user
- `DELETE /users/:id` - Delete user

## Key Concepts

### Modules

The application is organized into feature modules (Auth, Users) which encapsulate related functionality.

### Services

Business logic is contained in service classes that are injected into controllers via dependency injection.

### DTOs

Data Transfer Objects define the shape of request/response data and provide validation.

### Guards

Custom guards like JWT and Admin guards protect routes based on authentication and authorization rules.

### Entities

Database entities are defined with TypeORM decorators for automatic schema generation.

## Configuration

### Database Configuration

TypeORM is configured in the `AppModule` with PostgreSQL as the default database. Update the configuration in `app.module.ts` to use your database credentials.

### JWT Configuration

JWT tokens are used for authentication. Configure the secret key and expiration in your `.env` file.

## Next Steps

1. **Create Your Features** - Add new modules following the existing pattern
2. **Define Entities** - Create database entities in the entities folder
3. **Write Tests** - Add unit and e2e tests for your features
4. **Deploy** - Deploy to your preferred hosting platform (Heroku, AWS, etc.)

## Useful Resources

- [NestJS Documentation](https://docs.nestjs.com) - Official framework documentation
- [TypeORM Documentation](https://typeorm.io) - Database ORM documentation
- [PostgreSQL Documentation](https://www.postgresql.org/docs) - Database documentation
- [NestJS Community Discord](https://discord.gg/G7Qnnhy) - Get help from the community

## License

This project is [MIT licensed](LICENSE).
