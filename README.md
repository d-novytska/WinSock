# WinSock

This project is a console chat application based on WinSock and implemented in C++. 

It consists of two parts: a client and a server.

The technologies used in the project include `WSAStartup`, `SOCKADDR_IN`, and the `AF_INET` protocol. The server waits for incoming connections, accepts them, and sends data to clients. The client connects to the server using a specified IP address and port and can receive data from the server.

The core functionality of the project include:
1.	Running a server that listens on a specific port and waits for client connections.
2.	Launching client applications that connect to the server over the network.
3.	Allowing clients to send messages to the server.
4.	Enabling the server to relay received messages to all connected clients.

Description of the project:

- **Client-Server Architecture**: Application follows a client-server model. The server waits for incoming client connections, while clients initiate connections to the server.

- **WSAStartup**: I've used `WSAStartup` to initialize the WinSock library, allowing the program to work with networking operations within the Windows environment.

- **SOCKADDR_IN** and **AF_INET**: I've used the `SOCKADDR_IN` structure and the `AF_INET` protocol to define server and client network addresses and to work with IP addresses in the Internet protocol.

- **Array of SOCKET**: To manage multiple clients, maintaining an array of `SOCKET`, which represents the sockets through which the server communicates with each connected client.

- **Multithreading**: Implemented multithreading using the `CreateThread` function to handle message broadcasting. Each new client connection results in the creation of a new thread dedicated to receiving and processing messages from that client.

## Client_Server without limits

Client_Server without limits sends messages of any size, which is implemented by dynamically allocating memory. To determine the message size before it is received, the message size is recorded in a variable and sent before sending the message.
