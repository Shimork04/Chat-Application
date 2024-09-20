# **Java Based Real-Time Chat Application**

A console-based real-time chat application built using Java and TCP sockets. This application focuses on object-oriented programming (OOP) principles and design patterns, allowing users to create or join chat rooms, send and receive messages in real-time, and privately message other users.

## **Project Features**

- **User Authentication**: Users must register and log in using a username and password.
- **Real-Time Messaging**: Users in the same chat room can communicate in real-time. They can also send private messages.
- **Chat Rooms**: Users can create or join existing chat rooms using a room ID. Each chat room keeps a history of messages.
- **Private Messaging**: Users can send private messages to other users.
- **Active Users**: Users can view a list of active users in the chat room.
- **Message Persistence**: Chat messages are stored and can be retrieved when users rejoin the chat room.
- **Design Patterns**: Implements the Singleton, Observer, and Adapter design patterns for modular and flexible architecture.

## **Project Structure**

```bash
chat-application/
├── client/
│   └── ChatClient.java       # Client-side Java file for connecting to the server
├── controllers/
│   └── ClientHandler.java     # Handles interactions between client and server
├── models/
│   ├── ChatRoom.java          # Manages chat rooms
│   ├── ChatRoomManager.java   # Singleton class to manage all chat rooms
│   └── User.java              # Represents a user with username and password
├── network/
│   └── ChatServer.java        # Server-side code for handling client connections
├── services/
│   ├── MessageService.java    # Handles message broadcasting and private messages
│   └── UserManager.java       # Manages user registration and login
```

## **Technologies Used**

- **Java**: Core programming language used to develop the application.
- **TCP Sockets**: For real-time communication between the server and clients.
- **Object-Oriented Programming (OOP)**: Emphasis on modular, reusable code with OOP principles.
- **Design Patterns**:
  - **Singleton**: Ensures that only one instance of `ChatRoomManager` exists to manage chat rooms.
  - **Observer**: Notifies clients of new messages or users joining/leaving the room.
  - **Adapter**: Allows flexibility to handle different types of communication protocols.

## **Setup and Installation**

### 1. **Clone the Repository**

```bash
git clone https://github.com/Shimork04/chat-application.git
cd chat-application
```

### 2. **Compile the Application**

From the root directory of the project, compile all the Java files:

```bash
javac network/ChatServer.java controllers/ClientHandler.java models/ChatRoom.java models/ChatRoomManager.java models/User.java services/MessageService.java services/UserManager.java client/ChatClient.java
```

### 3. **Running the Chat Server**

To start the chat server, navigate to the root of your project and run the following command:

```bash
java network.ChatServer
```

The server will start and listen for client connections on port `12345`.

### 4. **Running the Chat Client**

In separate terminals, navigate to the `client/` folder and run the following commands to start client sessions:

```bash
cd client
java client.ChatClient
```

You can open multiple terminals to simulate multiple clients connecting to the chat server.

## **Usage Instructions**

### 1. **User Authentication**

When a user connects to the chat server, they are prompted to enter a username and password. If the username doesn't exist, the user is asked if they want to register. After successfully registering or logging in, the user is prompted to join or create a chat room by entering a room ID.

### 2. **Real-Time Messaging**

Once inside a chat room, users can send messages by typing into the console. All users in the room will see the messages in real-time.

### 3. **Private Messaging**

Users can send private messages to others by using the following command:

```bash
/msg <recipient_username> <message>
```

### 4. **Viewing Active Users**

Users can view the list of active users in the chat room by typing:

```bash
/active
```

### 5. **Exiting the Chat**

Users can leave the chat by typing:

```bash
exit
```

## **Features**

### User Authentication

- Users must register with a username and password.
- After registering, they can log in to access chat rooms.
- User credentials are managed by the `UserManager` class.

### Chat Rooms

- Users can create or join chat rooms by providing a room ID.
- The `ChatRoomManager` class handles the creation and management of chat rooms.
- Each chat room stores a list of active users and the message history.

### Real-Time Messaging

- Users in the same chat room can send and receive messages in real-time.
- The `MessageService` class handles message delivery and broadcasting to all users in the room.
- Private messaging between users is also supported.

### Active Users

- Users can view the list of active users in the chat room with the `/active` command.

### Message Persistence

- Chat messages are stored as history, allowing users to see past messages when they rejoin a room.

## **Design Patterns Used**

### 1. **Singleton Pattern**
The `ChatRoomManager` class ensures that only one instance of chat rooms is maintained across the system.

### 2. **Observer Pattern**
Users (observers) are notified of new messages or activities in the chat room, such as users joining or leaving.

### 3. **Adapter Pattern**
Allows flexibility to handle different types of communication protocols (e.g., TCP).
