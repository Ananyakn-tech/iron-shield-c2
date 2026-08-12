# TactiTrack C2
Real-time battlefield command and control dashboard for visualizing unit positions, planning optimal routes, and coordinating operations on a live map.

🔗 Live demo: https://tactitrack-c2.netlify.app

## Features
- Real-time unit tracking on an interactive map (Leaflet.js)
- Live updates across all connected clients via WebSockets (Socket.IO)
- Optimal route computation between units/waypoints using Dijkstra's algorithm
- Secure authentication with JWT
- Persistent data storage with MongoDB
- Command dashboard for monitoring and coordinating multiple units simultaneously

## Tech Stack
**Frontend:** JavaScript, Leaflet.js, Socket.IO Client
**Backend:** Node.js, Express, Socket.IO, MongoDB, JWT
**Deployment:** Netlify (frontend)

## Project Structure
```
TactiTrack-C2/
├── backend/     # Express server, Socket.IO, auth, Dijkstra routing logic, MongoDB models
├── frontend/    # Leaflet map UI, dashboard, real-time client
├── netlify.toml
└── .gitignore
```

## Getting Started

### Prerequisites
- Node.js (v16+)
- MongoDB (local instance or Atlas connection string)

### Installation

1. Clone the repo
```
git clone https://github.com/ananya-kn/TactiTrack-C2.git
cd TactiTrack-C2
```

2. Install backend dependencies
```
cd backend
npm install
```

3. Install frontend dependencies
```
cd ../frontend
npm install
```

4. Set up environment variables in `backend/.env`
```
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
PORT=5000
```

5. Run the backend
```
cd backend
npm start
```

6. Run the frontend
```
cd frontend
npm start
```

## How It Works
- Units/agents send location updates to the backend via Socket.IO.
- The backend broadcasts updates to all connected dashboards in real time.
- When a route is requested between two points, Dijkstra's algorithm computes the shortest path over the map graph and returns it to the client for rendering.
- JWT-based auth restricts dashboard access to authenticated operators.

## Author
**Ananya K N**

## License
MIT
