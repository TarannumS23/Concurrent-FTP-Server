# Concurrent FTP Server

A multi-client file transfer system developed in Java using TCP socket programming and multithreading.

## Overview

This project implements a client-server based file transfer system that allows clients to connect to a server and perform file management operations remotely.

The server uses Java `ServerSocket` and `Socket` for TCP communication. A separate thread is created to handle each connected client, allowing multiple clients to communicate with the server concurrently.

## Features

- Multi-client TCP communication
- File upload from client to server
- File download from server to client
- List files available on the server
- Check whether a file exists
- Display file information
- Display file size
- Rename files
- Delete files
- Client disconnection
- Command validation
- File transfer using Java I/O streams

## Supported Commands

| Command | Description |
|---|---|
| `LIST` | Displays files available on the server |
| `EXISTS <FileName>` | Checks whether a file exists |
| `INFO <FileName>` | Displays file information |
| `SIZE <FileName>` | Displays the size of a file |
| `GET <FileName>` | Downloads a file from the server |
| `PUT <FileName>` | Uploads a file to the server |
| `DELETE <FileName>` | Deletes a file from the server |
| `RENAME <OldFileName> <NewFileName>` | Renames a file |
| `QUIT` | Disconnects the client |

## Technologies Used

- Java
- Socket Programming
- TCP/IP
- Multithreading
- Java I/O
- File Handling

## Project Architecture

```text
                 TCP Connection
        ┌─────────────────────────────┐
        │                             │
        ▼                             ▼
┌──────────────┐              ┌──────────────┐
│    Client    │ ◄──────────► │    Server    │
│              │              │              │
│ FTPClient    │              │ FTPServer    │
└──────────────┘              └──────────────┘
                                     │
                         ┌───────────┼───────────┐
                         ▼           ▼           ▼
                      Client 1    Client 2    Client 3
                      Thread      Thread      Thread

Project Structure

Concurrent-FTP-Server/
│
├── FTPServer.java
├── FTPClient.java
├── README.md
└── .gitignore


* How to Run *

1. Compile the Server
Open a terminal in the project directory and run:

javac FTPServer.java

2. Compile the Client
javac FTPClient.java

3. Start the Server
java FTPServer

The server starts listening for client connections on port 9000.

4. Start the Client
Open another terminal in the same directory and run:

java FTPClient

5. Connect Multiple Clients
Additional clients can be started from separate terminals.

Each connected client is handled by a separate thread on the server.


Author

Tarannum Jakirhusen Shaikh