# node-postgres
My go to boilerplate project setup for Node ExpressJs and PostgreSQL stack.

## General directory setup

### API
  - path: `/config/api.js`
  - includes: `ExpressJs` app configuration
  - uses:
    - Everything above and below
    - `admin-bro` - admin dashboard panel configuration
    
### Configuration
  - path: `/config/config.js`
  - includes: Configuration specific constants, environment variables
  - uses
    - `Joi` - env validation

### DB connection
  - path: `/config/sequelize.js`
  - includes: DB configuration
  - uses:
    - `SequelizeJs`
    - `pg`

### Logging
  - path: `/config/log.js`
  - includes: Logging configuration
  - uses:
    - `morgan`

### Controllers
  - path: `/server/controllers/`
  - naming: `<controller-name>.controller.js`
  - includes: CRUD functions for models

### Models
  - path: `/server/models/`
  - naming: `<model-name>.model.js`
  - includes: Postgres table Schema

### Middlewares
  - path: `/server/middlewares/`
  - naming: `<middleware-name>.mware.js`
  - includes: API middleware logic
### Routes
  - path: `/server/routes/`
  - naming: `<model-route>.route.js`
  - includes: routes grouped by their logic

## Authorization

Authorization related setup.

### Libraries
  - path: `/src/express.js`
  - PassportJs JWT strategy
    - Easy to plug in
    - Easily can be replaced by any other strategy
### Routes
  - `/register`
  - `/login`
  - `/forgot-pwd`
  - `/reset-pwd`
  - `/verify`

### User Routes
Basepath: `/users`
  - `/` `GET` - get all users
  - `/` `POST` - create new user
  - `/:id` `GET` - get user by id
  - `/:id` `PATCH` - update user by id
  - `/:id` `DEL` - remove user by id
 
## MODELS
Models are placed in
### DB schemas
  - `User`
    #### Fields
      - `Name`
      - `Password`
      - `Email`
      - `...`

## DevOps
### Workflows
  - GitHub actions
    - Workflows for testing, publishing docker images, deploying
  
### Containering
  - `Dockerfile`
  - `docker-compose.yml`

### Scripting
  - `makefile` - useful commands for deploying, linting, testing

## Documentation

Swagger integration
