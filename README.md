# 💬 Real-Time Chat Application - For Learning Purpose

A simple real-time chat app built using Node.js, Express, and Socket.IO.
It allows users to send and receive messages instantly and shows who’s currently online in real time.

## Features

Real-time message sending and receiving

Shows which users are online

Broadcasts “user joined” and “user left” messages

Automatically updates online user list when someone joins or disconnects

Lightweight and easy to understand

## Tech Stack

Frontend: HTML, CSS, JavaScript

Backend: Node.js, Express.js

Real-time Engine: Socket.IO

## Installation

Clone the repository
```
git clone https://github.com/your-username/realtime-chat-app.git
cd realtime-chat-app
```

Install dependencies
```
npm install
```

Run the server
```
node server.js
```

Server will start on
 http://localhost:3000

Open multiple browser tabs or devices to test real-time messaging.

###  How It Works
1. Server Side (server.js)

Uses Express to create a server.

Integrates Socket.IO to handle real-time communication.

Listens for events:

connection → when a new user joins.

chat message → when a message is sent.

disconnect → when a user leaves.

2. Client Side (index.html)

Connects to the Socket.IO server.

Emits messages using socket.emit('chat message', msg)

Listens for updates using socket.on('chat message', ...)

Displays messages and the list of online users dynamically.

###  “Show Who’s Online” Feature

Each connected socket is tracked with a username.
When someone connects or disconnects:

The server updates the online users list.

It emits updateUsers event to all clients.

The frontend displays the live online users list.

Example:
```
socket.on('updateUsers', (users) => {
  const userList = document.getElementById('users');
  userList.innerHTML = users.map(u => `<li>${u}</li>`).join('');
});
```
### 📂 Project Structure
│── index.html  
├── server.js
├── package.json
└── README.md

 ### Example
 Output Preview
<img width="1918" height="911" alt="image" src="https://github.com/user-attachments/assets/8d7a61d0-473b-4d27-bdd8-fdc692229ae6" />

Open two tabs

Type messages → both sides will see them instantly

You’ll also see when users join or leave

### 📜 License

This project is open-source and free to use for learning and development.
