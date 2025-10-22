# Task Manager

A simple task management application built with Next.js frontend and Express backend, using Prisma ORM with PostgreSQL database.

## Project Structure

```
task-manager/
├── backend/          # Express.js API server
├── frontend/         # Next.js React application
└── docker-compose.yml # PostgreSQL database configuration
```

## Features

- ✅ Create, read, update, and delete tasks
- ✅ Mark tasks as complete/incomplete
- ✅ Modern UI with Tailwind CSS
- ✅ TypeScript support
- ✅ PostgreSQL database with Prisma ORM
- ✅ Docker containerized database

## Prerequisites

- Node.js (v18 or higher)
- Docker and Docker Compose
- npm or yarn

## Setup Instructions

### 1. Start the Database

```bash
# Start PostgreSQL database using Docker
docker compose up -d
```

### 2. Setup Backend

```bash
cd backend

# Install dependencies
npm install

# Generate Prisma client
npx prisma generate

# Run database migrations
npx prisma migrate dev

# Start the development server
npm run dev
```

The backend API will be available at `http://localhost:3001`

### 3. Setup Frontend

```bash
cd frontend

# Install dependencies
npm install

# Start the development server
npm run dev
```

The frontend application will be available at `http://localhost:3000`

## API Endpoints

- `GET /api/tasks` - Get all tasks
- `GET /api/tasks/:id` - Get a specific task
- `POST /api/tasks` - Create a new task
- `PUT /api/tasks/:id` - Update a task
- `DELETE /api/tasks/:id` - Delete a task
- `GET /health` - Health check endpoint

## Database Schema

The application uses a simple Task model with the following fields:

- `id` (String, Primary Key)
- `title` (String, Required)
- `description` (String, Optional)
- `completed` (Boolean, Default: false)
- `createdAt` (DateTime)
- `updatedAt` (DateTime)

## Development

### Backend Development

```bash
cd backend
npm run dev  # Starts server with nodemon for auto-restart
```

### Frontend Development

```bash
cd frontend
npm run dev  # Starts Next.js development server
```

### Database Management

```bash
cd backend

# View database in Prisma Studio
npx prisma studio

# Reset database
npx prisma migrate reset

# Create new migration
npx prisma migrate dev --name your_migration_name
```

## Production Deployment

1. Build the frontend:
   ```bash
   cd frontend
   npm run build
   ```

2. Start the backend in production:
   ```bash
   cd backend
   npm start
   ```

3. Ensure PostgreSQL is running and accessible

## Environment Variables

### Backend (.env)
```
DATABASE_URL="postgresql://postgres:password@localhost:5432/taskmanager?schema=public"
PORT=3001
```

## Technologies Used

- **Frontend**: Next.js 14, React, TypeScript, Tailwind CSS
- **Backend**: Express.js, Node.js
- **Database**: PostgreSQL
- **ORM**: Prisma
- **Icons**: Lucide React
- **HTTP Client**: Axios
- **Containerization**: Docker
