# Concurrent Socket Server

A Java client-server application that demonstrates **socket programming, multithreading, and concurrent request processing**.

The project consists of a server and client. The server listens for incoming socket connections and creates a separate thread to handle each client request. The client can generate multiple concurrent requests and measure the turnaround time of those requests.

## Project Overview

The purpose of this project was to explore how a server can handle multiple client connections concurrently using Java threads.

The server accepts a port number and continuously waits for incoming client connections. When a client connects, the server creates a `ClientHandler` thread to process the request.

The client connects to the server using a specified network address and port. It allows the user to select a system command and specify the number of concurrent requests to send.

## Technologies Used

* Java
* Socket Programming
* TCP/IP Networking
* Multithreading
* Client-Server Architecture

## Features

### Concurrent Server

The server uses Java's `ServerSocket` and `Socket` classes to establish network communication.

Each incoming client connection is assigned its own `ClientHandler` thread, allowing the server to handle multiple clients concurrently.

### Client Requests

The client provides several commands that can be requested from the server:

1. Date and Time
2. Uptime
3. Memory Use
4. Netstat
5. Current Users
6. Running Processes
7. Exit

These commands are sent to the server through socket connections.

### Concurrent Requests

The client allows the user to specify the number of requests to send. It creates a separate Java thread for each request and starts the threads concurrently.

### Performance Measurement

The client records the turnaround time for each request and calculates the total and average turnaround time after all request threads finish.

## How It Works

The client can create multiple threads, with each thread establishing its own socket connection to the server. The server then creates a corresponding handler thread for each connection.

## Server Commands

The server executes the following commands:

| Command | Operation           |
| ------- | ------------------- |
| 1       | Date and Time       |
| 2       | System Uptime       |
| 3       | Memory Usage        |
| 4       | Network Connections |
| 5       | Current Users       |
| 6       | Running Processes   |

The server executes the selected command and sends the resulting output back to the client.

## Running the Project

### 1. Compile the Java files

```bash
javac Server.java Client.java
```

### 2. Start the Server

```bash
java Server
```

The server will prompt for a port number:

```text
Enter port number:
```

Enter the port you want the server to listen on.

### 3. Start the Client

In another terminal:

```bash
java Client
```

The client will ask for:

```text
Please Enter Network Address:
Please Enter Port:
```

Enter the server's network address and the same port used by the server.

### 4. Select a Command

The client will display the available commands:

```text
1 - Date and Time
2 - Uptime
3 - Memory Use
4 - Netstat
5 - Current Users
6 - Running Process
7 - Exit Program
```

### 5. Select the Number of Requests

The client allows multiple requests to be generated:

```text
Options: 1, 5, 10, 15, 20, 25
```

The requests are processed concurrently using multiple threads.

## Performance Results

The client measures the turnaround time of each request and reports:

* Total turnaround time
* Average turnaround time
* Individual request turnaround times

This allows the performance of concurrent requests to be observed and compared.

## Concepts Demonstrated

This project demonstrates several important computer science concepts:

* Client-server architecture
* TCP socket communication
* Network programming
* Java `ServerSocket` and `Socket`
* Multithreading
* Concurrent request processing
* Thread synchronization
* Performance measurement
* Operating system commands

## Project Structure

```text
Concurrent-Socket-Server/
│
├── Server.java
├── Client.java
└── README.md
```

## Disclaimer

This project was developed for educational purposes to demonstrate concurrent networking and multithreading concepts in Java.
