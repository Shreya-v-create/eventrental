# Event Equipment Rental

A site for renting event equipment (sound, lighting, stages, tents, tables & chairs, projectors, generators and decor). It has a React/Vite frontend and an Express/Mongoose API.

## Setup

1. Install Node.js 20+.
2. Install everything once from the project root: `npm install`
3. Add the sample equipment and the admin user: `npm run seed`
4. Start the backend and frontend together: `npm run dev`
5. Open `http://localhost:5173`

The MongoDB Atlas connection string is the `MONGO_URL` line at the top of `backend/server.js`. If you get a connection error, check that your current IP address is allowed in Atlas → **Network Access**.

## Admin login

After `npm run seed`, log in with:

- Email: `admin@eventrental.com`
- Password: `admin123`

## Where things are

- `backend/server.js` holds everything on the server: the models (User, Equipment, Booking), the API routes, the admin check and the sample data.
- `frontend/src/App.jsx` holds every page: Home, Catalog, Equipment detail, Cart, Login, Register, My bookings and Admin.
- `frontend/src/styles.css` holds all the styles.

The API listens on port 5000. Vite forwards `/api` requests to it. The logged-in user and the cart are saved in the browser's localStorage. For admin actions, the frontend sends the user's id in an `x-user-id` header and the server checks that this user is an admin.

`npm run seed` deletes all equipment and bookings before adding the sample items. Customer accounts are kept.
