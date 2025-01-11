# P2P File Sharing Application

## Overview
This P2P (Peer-to-Peer) file sharing application is built in Python and combines networking capabilities with a graphical user interface. It allows users to discover other peers on their network automatically and share files between them. The application uses both TCP for reliablebfile transfers and UDP for peer discovery, making it a hybrid networking solution.

### Core Classes
The application is structured around two main classes: P2PNodeGUI and P2PNode. The P2PNodeGUI class handles all user interface elements and interactions, while the P2PNode class manages the actual networking and file transfer operations. This separation makes the code more maintainable and easier to understand.

### GUI
The GUI presents users with a clean, functional interface containing several key elements: a port configuration field (defaulting to 5000), a "Start Node" button to initialize the P2P node, a file selection button, and a "Send File" button for initiating transfers. There's also a text area that displays logging information, keeping users informed about ongoing operations and any errors that might occur. The GUI is designed to be intuitive, with clear labels and straightforward controls.

### Peer Discovery
The peer discovery mechanism uses UDP broadcasting to announce a node's presence on the network. Every second, each node broadcasts a JSON message containing its IP address and port number. Simultaneously, nodes listen for these broadcast messages from other peers. When a new peer is discovered, the application automatically initiates a connection to that peer. This creates a dynamic, self-organizing network where peers can join and leave freely.

### File Transfer
File transfers are handled through TCP connections to ensure reliability. When a user selects a file to send, the application randomly chooses a peer from its known peers list and establishes a TCP connection. The file is sent in chunks of 4096 bytes, with proper error handling at each step. On the receiving end, files are saved with a "received_" prefix to avoid naming conflicts. The chunked transfer approach allows for handling large files efficiently while maintaining memory efficiency.

### Connection Management
The application manages connections through a threading system. Each incoming connection is handled in a separate thread, allowing the node to handle multiple transfers simultaneously. The connection handler first determines the type of incoming connection (either a new peer connecting or a file transfer request) and then processes it accordingly. This threaded approach ensures that the application remains responsive during file transfers and peer discovery operations.

### Error Handling
Throughout the application, error handling is implemented using try-except blocks. All network operations, file operations, and peer communications are wrapped in error handling code to ensure the application remains stable even when things go wrong. A logging system keeps track of all operations, errors, and status updates, displaying them in the GUI's text area for user awareness.

## Features
- Start a P2P nodes on devices in the network
- Select files to share to the netowrk
- Send files to other nodes

## Requirements
- Python 3.x
- Tkinter
- socket
- threading
- json
- os
- time
- random
- typing

## Installation
1. Clone the repository:
   ```
   git clone https://github.com/HasanZiyade/p2p-file-sharing.git
   ```
2. Navigate to the project directory:
   ```
   cd p2p-file-sharing
   ```
3. Install the required dependencies:
   ```
   pip install -r requirements.txt
   ```

## Usage
1. Run the application on the devices in the network:
   ```
   python src/maingui.py
   ```
2. Enter unique port number for the respective node on each device and click "Start Node".
3. Select a file to share and click "Send File".
