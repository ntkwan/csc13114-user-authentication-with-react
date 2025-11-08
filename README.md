# csc13114-user-authentication-with-react
A complete user registration and authentication system built with modern technologies.

## Prerequisites
Before running this project, make sure you have the following installed:
- Node.js (version 18 or higher)
- npm or yarn
- PostgreSQL (version 14 or higher)

## Installation

### 1. Clone the repository

```bash
git clone <repository-url>
cd csc13114-user-authentication-with-react-
```

### 2. Setup PostgreSQL database

Create a new PostgreSQL database:

```bash
psql -U postgres
CREATE DATABASE user_auth_db;
\q
```

### 3. Backend setup

Navigate to the server directory and install dependencies:

```bash
cd server
npm install
```

Create a `.env` file in the server directory:

```bash
cp .env.example .env
```

Update the `.env` file with your database credentials:

```
DATABASE_HOST=localhost
DATABASE_PORT=5432
DATABASE_USER=postgres
DATABASE_PASSWORD=your_password
DATABASE_NAME=user_auth_db
PORT=3001
FRONTEND_URL=http://localhost:3000
```

### 4. Frontend setup

Navigate to the client directory and install dependencies:

```bash
cd ../client
npm install
```

Create a `.env.local` file in the client directory:

```bash
cp .env.local.example .env.local
```

The file should contain:

```
NEXT_PUBLIC_API_URL=http://localhost:3001
```

## Running the application

### Start the backend server

In the server directory:

```bash
npm run start:dev
```

The backend will run on `http://localhost:3001`

### Start the frontend application

In the client directory:

```bash
npm run dev
```

The frontend will run on `http://localhost:3000`

## Usage

1. Open your browser and navigate to `http://localhost:3000`
2. Click on "Sign up" to create a new account
3. Fill in your email and password (minimum 6 characters)
4. Click "Sign up" to register
5. After successful registration, you will be redirected to the login page
6. Enter your credentials to login (UI only, backend logic not required)

## Development

### Backend

The backend uses TypeORM with synchronize enabled, which automatically creates database tables based on entity definitions. In production, you should use migrations instead.

### Frontend

The frontend uses the Next.js App Router with server and client components. All pages with user interaction are client components.

### CORS error

Make sure the `FRONTEND_URL` in the backend `.env` file matches the frontend URL.