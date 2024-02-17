# Real-Time Chat Application with gRPC

## Overview

This project is a real-time chat application built using gRPC (Google Remote Procedure Call) in Golang. The application allows users to join different chat rooms, send messages, and receive messages in real-time. Users can create private chat rooms or join public ones, enabling seamless communication in both personal and group settings.

## Features

- **User Authentication and Authorization:** Secure user authentication using JWT (JSON Web Tokens) ensures secure communication between clients and the server. User roles and permissions control access to features such as creating private rooms.
  
- **Chat Rooms Management:** Users can create, join, and leave chat rooms. The application supports both public and private chat rooms, with options for defining room permissions like read-only or moderator privileges.

- **Real-Time Messaging:** Utilizing bidirectional streaming RPCs in gRPC, the application enables real-time messaging between clients and the server. Message broadcasting delivers messages to all users in a chat room, while private messaging allows direct communication between specific users.

- **Message Persistence:** Chat messages are stored in a database to maintain message history. The application provides APIs to retrieve previous messages when joining a chat room, ensuring a seamless user experience.

- **User Presence and Notifications:** The application tracks user presence in chat rooms, displaying online/offline status. Notifications inform users of new messages, mentions, or other relevant events, enhancing user engagement.

## Technical Architecture

### Directory Structure

```
chat-app/
├── cmd/
│   └── server/
│       └── main.go
├── internal/
│   ├── auth/
│   │   ├── jwt.go
│   │   └── auth.go
│   ├── chat/
│   │   ├── room.go
│   │   └── chat.go
│   ├── db/
│   │   └── repository.go
│   ├── model/
│   │   ├── user.pb.go
│   │   ├── chat.pb.go
│   │   └── ...
│   └── server/
│       ├── server.go
│       ├── middleware.go
│       └── handlers.go
├── pkg/
│   └── middleware/
│       └── auth.go
├── proto/
│   ├── user.proto
│   ├── chat.proto
│   └── ...
├── config/
├── tests/
├── docs/
├── README.md
├── go.mod
└── go.sum
```

### Components

- **cmd/server/main.go:** Main entry point for the gRPC server, responsible for initializing the server and starting to listen for incoming connections.

- **internal/:** Contains internal packages/modules for application logic.

  - **auth/:** Authentication logic, including JWT implementation and authentication service interface.
  - **chat/:** Chat room management and messaging logic, including room management and chat service interface.
  - **db/:** Database interactions, including database repository interface.
  - **model/:** Protobuf message definitions for user-related and chat-related messages.
  - **server/:** gRPC server implementation, including server setup, middleware, and service method implementations.

- **pkg/:** Reusable packages/modules shared across different parts of the application, such as middleware, utilities, etc.

- **proto/:** Protobuf definition files (.proto) for defining service interfaces and message types.

### Technologies Used

- **Language:** Go (Golang)
- **gRPC:** Google's high-performance, open-source universal RPC framework
- **Protocol Buffers (Protobuf):** Language-neutral, platform-neutral, extensible mechanism for serializing structured data
- **JWT (JSON Web Tokens):** Secure method for transmitting information between parties as JSON objects
- **Database:** (Choose a suitable database for your application, e.g., PostgreSQL, MongoDB)
- **Docker:** Containerization platform for building, shipping, and running applications
- **Kubernetes (Optional):** Container orchestration platform for managing containerized workloads and services

## Usage

1. **Clone the Repository:**
   ```bash
   git clone <repository-url>
   cd chat-app
   ```

2. **Build and Run the Server:**
   ```bash
   go build ./cmd/server
   ./server
   ```

3. **Run the Client Application:**
   - Develop client applications for various platforms (e.g., web, mobile, desktop) using gRPC clients in different programming languages.

4. **Interact with the Chat Application:**
   - Join public or private chat rooms.
   - Send and receive messages in real-time.
   - View message history and user presence.

## Documentation

For detailed API documentation, deployment instructions, and other relevant information, refer to the [docs](./docs) directory.

## Contributing

Contributions are welcome! For major changes, please open an issue first to discuss potential changes and improvements.

## License

This project is licensed under the [MIT License](./LICENSE).
