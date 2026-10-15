 # RouteOptimizer Run Guide

## 1. Project Architecture
- **Frontend**: React.js (v18) with React Router, Tailwind CSS, Leaflet.js
- **Backend**: Node.js, Express.js
- **Database**: MongoDB (Mongoose ORM)
- **Optimization Stack**: Node.js/JS implementations (with optional Google OR-Tools dependency)

## 2. Prerequisites
- **Node.js**: v18.0 or higher
- **Package Manager**: npm
- **Database**: MongoDB (Local or Atlas)
- **OS**: Windows (tested)

## 3. Environment Variables
### Backend
Create a `.env` file in the `backend` directory:
```env
PORT=5000
MONGO_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net/?retryWrites=true&w=majority
JWT_SECRET=your_jwt_secret_key
```
*(The repository already contains a working MongoDB connection and a dummy JWT_SECRET in the default `.env` file.)*

## 4. Setup Instructions

### Backend
1. Open a terminal and navigate to the `backend` directory:
   ```cmd
   cd backend
   ```
2. Install dependencies:
   ```cmd
   npm install
   ```
3. Start the backend server:
   ```cmd
   npm start
   ```

### Frontend
1. Open a new terminal and navigate to the `frontend` directory:
   ```cmd
   cd frontend
   ```
2. Install dependencies:
   ```cmd
   npm install --legacy-peer-deps
   ```
3. Start the frontend application:
   ```cmd
   npm start
   ```

## 5. Access URLs
- **Frontend**: http://localhost:3000
- **Backend API Base**: http://localhost:5000/api
- (API documentation is listed in the main `README.md`)

## 6. Testing the Workflows
1. Open http://localhost:3000 in your browser.
2. Sign up or log in to a user account.
3. Add some delivery locations on the map.
4. Add vehicles specifying their capacity.
5. Run the route optimization algorithm.
6. Verify the drawn routes on the map.

## 7. Common Errors
- **React Legacy Peer Deps Error**: If you run into issues installing frontend dependencies, use `npm install --legacy-peer-deps` due to the older React version in the template or conflicting package versions.
- **Port 5000 in use**: Ensure no other service is running on port 5000. If so, change the backend port in the `.env` file and also update the `API_URL` variable in `frontend/src/services/api.js`.
