# HotelPro – Hotel Booking and Management System

**Project By:** Mayank Verma  
**Email:** en24cs3010622@medicaps.ac.in  
**University:** Medicaps University  
**Project Type:** Academic Web Development Project

---

## 1. Introduction

HotelPro is a web-based hotel booking and management project developed as part of my learning in web development. The main idea is to make the room booking process easier for customers and provide a basic dashboard for managing hotel rooms and reservations.

Customers can explore available rooms, make bookings, and manage their reservations. The administrator section is intended for handling room information, customer bookings, and registered users.

## 2. Project Goals

- Provide a simple interface for browsing and booking hotel rooms.
- Store room, user, and booking information in a database.
- Keep customer features separate from administrator features.
- Check booking dates to help avoid overlapping reservations.
- Practise frontend development, backend APIs, authentication, and database integration.

## 3. Technologies Used

| Technology | Use in the Project |
| --- | --- |
| React and Vite | Frontend interface |
| Bootstrap | Page layout and styling |
| Node.js | Backend JavaScript runtime |
| Express.js | API and server routes |
| MongoDB / MongoDB Atlas | Application database |
| Mongoose | Database models and connection |
| JWT | Authentication tokens |
| bcryptjs | Password hashing |
| Axios | Requests from frontend to backend |

## 4. Main Modules

### Customer Module

- Sign up and log in.
- Browse hotel rooms and view room details.
- Filter rooms using available options such as room type, price, and dates.
- Book a room by selecting check-in and check-out dates.
- View or cancel personal bookings.
- Access a personal dashboard.

### Admin Module

- View hotel and booking summary information.
- Add, edit, and remove room details.
- Update room availability.
- View customer bookings.
- View registered users and their roles.

## 5. Project Folder Structure

```text
HotelPro-main/
├── Client/       # React frontend
├── Server/       # Express backend and API
├── package.json  # Root-level commands
└── README.md
```

## 6. Requirements

Before running the project, make sure these are available:

- Node.js v18 or newer
- npm
- A MongoDB database, either MongoDB Atlas or a local installation

## 7. Installation and Setup

### Step 1: Install backend dependencies

Open a terminal in the project folder and run:

```bash
cd Server
npm install
```

### Step 2: Install frontend dependencies

```bash
cd ../Client
npm install
```

### Step 3: Configure MongoDB

Create or open `Server/.env` and add your local configuration. Replace the example MongoDB value and secret with your own values.

```env
PORT=5000
MONGODB_URI=your_mongodb_atlas_connection_string
JWT_SECRET=replace_with_a_long_random_secret
JWT_EXPIRES_IN=7d
CLIENT_URL=http://localhost:5173
NODE_ENV=development
```

In MongoDB Atlas, check that your database user has the required permissions and that your IP address is allowed under Network Access.

**Security note:** Do not commit your real database connection string, database password, or JWT secret to a public repository.

### Step 4: Start the backend

In a terminal, run:

```bash
cd Server
npm start
```

The backend is expected to run at `http://localhost:5000`. The health-check endpoint is `http://localhost:5000/api/health`.

### Step 5: Start the frontend

Open a second terminal and run:

```bash
cd Client
npm run dev
```

Vite will display the frontend URL. It is usually `http://localhost:5173`.

## 8. Useful Commands

Run each command from the appropriate folder.

```bash
# Start backend
cd Server
npm start

# Run backend tests
npm test

# Start frontend in a separate terminal
cd Client
npm run dev

# Create a production frontend build
npm run build
```

## 9. API Overview

| Module | Example endpoints | Purpose |
| --- | --- | --- |
| Authentication | `/api/auth/signup`, `/api/auth/login`, `/api/auth/me` | User registration and login |
| Rooms | `/api/rooms`, `/api/rooms/:id` | View and manage room information |
| Bookings | `/api/bookings`, `/api/bookings/my` | Create and view bookings |
| Administration | `/api/admin/users`, `/api/admin/stats` | Admin user and summary data |

Some endpoints require a valid login token. Administrator endpoints require an administrator account.

## 10. Database and Booking Process

MongoDB is used to store user, room, and booking data. Mongoose is used for database models and communication with MongoDB. The backend validates booking dates, calculates the duration and total amount, and checks for overlapping reservations before accepting a booking.

## 11. Testing

The backend test suite can be started with:

```bash
cd Server
npm test
```

The documented test areas include authentication, duplicate registrations, room permissions, booking date validation, price calculation, overlapping reservations, cancellation, and administrator access. Actual results depend on the project's current configuration and test setup.

## 12. Possible Future Enhancements

- Integrate an online payment gateway.
- Send booking confirmations by email or SMS.
- Improve mobile responsiveness and accessibility.
- Add customer reviews and ratings.
- Deploy the frontend and backend for online access.

## 13. Conclusion

HotelPro brings together the main parts of a basic hotel booking system: a customer-facing interface, room and booking management, backend APIs, and database connectivity. Working on this project provides practical experience with the MERN-style development workflow and gives scope for further improvements.

---

*Prepared by Mayank Verma | Medicaps University*
