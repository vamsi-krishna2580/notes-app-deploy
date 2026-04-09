# Notes App Deployment

This project deploys a full-stack Notes App using Docker Compose with three services:

- **MongoDB** – Database service
- **Backend** – Node.js API server
- **Frontend** – Vite frontend application

---

## Project Structure

For project structure refer this [Repo](https://github.com/vamsi-krishna2580/MERN/tree/main/notes-app)

---

## Environment Setup

### Backend Environment Variables

Create `backend/.env` from `backend/.env.example`:

```env
PORT=
MONGODB_URI=
UPSTASH_REDIS_REST_URL=
UPSTASH_REDIS_REST_TOKEN=
JWT_SECRET=
```

Example:

```env
PORT=3000
MONGODB_URI=mongodb://mongo:27017/notesdb
UPSTASH_REDIS_REST_URL=your_upstash_url
UPSTASH_REDIS_REST_TOKEN=your_upstash_token
JWT_SECRET=your_secret_key
```

---

### Frontend Environment Variables

Create `frontend/.env` from `frontend/.env.example`:

```env
VITE_API_URL=
```

Example:

```env
VITE_API_URL=http://localhost:3000
```

---

## Docker Compose Configuration

The app uses the following services:

- `mongo` → MongoDB container
- `backend` → Backend API container
- `frontend` → Frontend UI container

Start all services:

```bash
docker-compose up -d
```

Stop all services:

```bash
docker-compose down
```

---

## Access URLs

After starting the containers:

- Frontend: http://localhost:5173
- Backend: http://localhost:3000
- MongoDB: mongodb://localhost:27017

---

## Docker Images Used

- `mongo`
- `vamsi8121/notes-app-backend:latest`
- `vamsi8121/notes-app-frontend:latest`

---

## Notes

- Ensure Docker and Docker Compose are installed before running.
- MongoDB hostname inside Docker network is `mongo`.
- Backend depends on MongoDB.
- Frontend depends on Backend.

---

## Deployment Steps Summary

1. Copy env files:
   ```bash
   cp backend/.env.example backend/.env
   cp frontend/.env.example frontend/.env
   ```

2. Update environment variables.

3. Run:
   ```bash
   docker-compose up -d
   ```

4. Open in browser:
   ```bash
   http://localhost:5173
   ```
