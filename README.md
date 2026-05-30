# 📍 Live Location Tracker

A real-time location tracking web application built with **Node.js**, **Socket.IO**, and **Leaflet.js**. Track multiple users simultaneously on an interactive map — each user appears as a live marker that updates in real time.

## 🚀 Live Demo

> **[Try it live →](YOUR_RENDER_URL_HERE)**
>
> Open on multiple devices to see real-time multi-user tracking in action!

## ✨ Features

- 🗺️ **Real-time location tracking** on an interactive OpenStreetMap
- 👥 **Multi-user support** — each connected user gets their own marker
- 🔄 **Live updates** via WebSocket (Socket.IO)
- 📱 **Works on mobile** — open on your phone and laptop to see both markers
- 🧹 **Auto-cleanup** — markers are removed when users disconnect

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| **Node.js** | Server runtime |
| **Express.js** | Web framework |
| **Socket.IO** | Real-time WebSocket communication |
| **Leaflet.js** | Interactive map rendering |
| **EJS** | Template engine |
| **OpenStreetMap** | Map tile provider |

## 📦 Installation

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/live-tracker.git

# Navigate to the project
cd live-tracker

# Install dependencies
npm install

# Start the server
node app.js
```

Open `http://localhost:3000` in your browser and allow location access.

## 🧪 How to Test Multi-User

1. Open the app on your **laptop browser**
2. Open the same URL on your **phone** (both must be on the same network for localhost, or use the deployed link)
3. Watch both markers appear on the map in real time!

## 📁 Project Structure

```
live-tracker/
├── app.js                  # Server — Express + Socket.IO setup
├── public/
│   ├── css/
│   │   └── style.css       # Full-screen map styling
│   └── js/
│       └── script.js       # Client — Geolocation + map logic
├── views/
│   └── index.ejs           # HTML template with Leaflet
├── package.json
└── README.md
```

## ⚙️ How It Works

1. **Client** requests geolocation via `navigator.geolocation.watchPosition()`
2. **Client** emits coordinates to the server via Socket.IO (`send-location`)
3. **Server** broadcasts the location to all connected clients (`receive-location`)
4. **Client** renders/updates markers on the Leaflet map
5. On **disconnect**, the server notifies all clients to remove the marker

## 📄 License

MIT
