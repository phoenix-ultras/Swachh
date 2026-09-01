# 🧹 Swachh - Civic Cleanliness Issue Reporting Platform

Swachh is a multi-platform civic issue reporting application connecting citizens directly with municipal corporations (**Nagar Nigam**). Citizens can report cleanliness issues by taking photos, tagging GPS coordinates, and tracking cleanup progress in real-time.

---

## ✨ Features

- 📸 **Issue Reporting**: Capture/upload photos, set titles, descriptions, and automatic GPS location coordinates.
- ⚡ **Real-Time WebSockets Sync**: Live feed updates using `socket.io` when complaints are submitted, upvoted, or marked resolved.
- 🔐 **Role-Based Access Control (RBAC)**: JWT authentication for **Citizen** and **Sanitation Worker** roles.
- ⌛ **Status Lifecycle Tracking**: Complaint status flow: **Pending** ⌛ ➔ **In Progress** 🛠️ ➔ **Resolved** ✅.
- 👍 **Community Upvoting**: Neighborhood residents can upvote issues to highlight high-priority garbage hotspots.
- 🗺️ **Google Maps Navigation**: Direct "Directions" button launching turn-by-turn map navigation targeting complaint coordinates.
- 🌐 **Multi-Platform Ready**: Runs seamlessly on **Web (Chrome/Edge)**, **Android**, **iOS**, and **Desktop**.

---

## 🛠️ Technology Stack

- **Frontend**: Flutter (Dart), Riverpod, Google Maps API, `socket_io_client`, `http`, `flutter_dotenv`.
- **Backend**: Node.js, Express.js, PostgreSQL (`pg`), Socket.io, Multer, Sharp, JWT (`jsonwebtoken`), `bcryptjs`.
- **Database**: PostgreSQL relational database schema (`users`, `complaints`, `upvotes`).

---

## 🚀 Quick Start Guide

### 1. Database Setup
1. Ensure PostgreSQL is installed and running locally.
2. Create a database named `swachh`.
3. Import the table schema:
   ```bash
   psql -U postgres -d swachh -f server/schema.sql
   ```

### 2. Start Backend REST & WebSockets Server
```bash
cd server
npm install
npm start
```
*Server runs on `http://localhost:3000/api` with static image uploads served at `http://localhost:3000/uploads`.*

### 3. Run Flutter Application

#### Run on Web:
```bash
flutter pub get
flutter run -d chrome
```

#### Run on Android / iOS:
```bash
flutter pub get
flutter run -d android
```

---

## 📄 Environment Configuration

Create a `.env` file in the root project folder:
```env
BACKEND_URL=http://localhost:3000/api
MAP_API_KEY=YOUR_GOOGLE_MAPS_API_KEY
```

Create a `.env` file inside `server/`:
```env
PORT=3000
JWT_SECRET=your_jwt_secret_key
PGUSER=postgres
PGHOST=localhost
PGDATABASE=swachh
PGPASSWORD=postgres
PGPORT=5432
```
# Swachh
