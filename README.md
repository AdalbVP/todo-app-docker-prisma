#Todo App - Node.js + Prisma + PostgreSQL + Docker

This project implements a **Task Management RESTful API (CRUD)** using **Express**, **PostgreSQL** as the relational 
database, and **Prisma ORM** as the data access layer.
The entire application is **Containerized with Docker and Docker Compose**, making deployment and portability easier.

---

## Technologies Used
- **Node.js + Express** - Framework to build the REST API.
- **PostgreSQL** - Relational Database.
- **Prisma ORM** - Data modeling, migrations, and queries.
- **docker + Docker Compose** - Containerization and orchestration.
- **REST Client (VS code)** - API testing with `Todo-app.rest`.

---

##Project Structure
│
├── public/
│   └── index.html              # The frontend HTML file for authentication and todo management
│
├── prisma/
│   ├── schema.prisma           # The frontend HTML file for authentication and todo management
│   └── migrations/             #
│
├── src/
│   ├── controllers/            # (Optional) For future separation of concerns
│   └── middlewares/
│       └── authMiddleware.js    # Middleware for verifying JWT and protecting routes
│   └── routes/
│       └── authRoutes.js        # Routes for user registration and login
│       └── todoRoutes.js        # Routes for authenticated CRUD operations on todos
│   └── prismaClient.js          # Prisma client database setup and table creation
│   └── server.js                # Main server entry point that sets up routing and middleware
│
├── Dockerfile                   # Docker container setup instructions
├── docker-compose.yaml          # Docker setup config file
├── package.json                 # Project dependencies and scripts
├── package-lock.json            # Lockfile for exact dependency versions
└── todo-app.rest                # REST client file for emulating API requests

---

##Setup & Installation

###1. Clone the repository
``bash
git clone https://github.com/AdalbVP/todo-app-docker-prisma.git
cd todo-app-docker-prisma

###2. Generate Prisma Client
npx prisma generate

###3. Build your docker images
docker compose build

###4. Create PostgreSQL migrations and apply them 
docker compose run app npx prisma migrate dev --name init

###5. Boot up docker containers 
docker compose up

###6. To login docker PosgreSQL database
docker exec -it postgres-db psql -U postgres -d todoapp

###7. To stop docker containers
docker compose down

###8. Access the app 
Open http://localhost:5003 in your browser

---

##License 
This project is for educational purposes and part of my backend development practice.
It is based on ideas and concepts from James MCArthur's course, adapted and implemented for my portfolio.
