# Communication Networks Project 2021/2022 - Stock Exchange Simulation

## Authors
- Ricardo Rafael Ferreira Guegan
- Rui Pedro Capelas Santos


## Overview
This project implements a stock exchange simulation with TCP and UDP connections. TCP is used for client interactions, while UDP is for administrator commands.

## Administrator Commands
- `ADD_USER`: Create/update a user.
- `DEL`: Delete a user.
- `LIST`: List all users.
- `REFRESH`: Change the refresh time.
- `QUIT`: Exit the console.
- `QUIT_SERVER`: Shut down the server.

## Client Commands
- `COMPRAR`: Buy stocks in the format `name-quantity-price`.
- `VENDER`: Sell stocks in the same format.
- `INFO`: Display owned stocks and available balance.
- `DADOS ON/OFF`: Join/leave multicast groups.
- `SAIR`: Exit the console.

## Implementation Details
The project consists of 4 C files and a header file with structures and global variables. The server (`Servidor_RC.c`) initializes shared memory and sockets for multicast communication and creates processes for UDP and TCP calls. A thread updates stock values and sends them to users via multicast.

The `connectTCP.c` file handles client interactions with a TCP socket (port 9876), managing user requests and controlling simultaneous users (max 5). The `connectUDP.c` file allows the administrator to manage the server with a UDP socket (port 9000).

The `cliente.c` file sets up a TCP socket for client-server communication.

## Network Configuration
Using GNS3, routers and PCs were configured to ensure a robust connection between PCs and the SERVER[^2^][2]. Router R2 was set up with SNAT, and multicast configurations were applied to all routers.
