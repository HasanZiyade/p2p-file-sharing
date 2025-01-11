# P2P File Sharing Application

## Overview
This P2P (Peer-to-Peer) file sharing application is built in Python and combines networking capabilities with a graphical user interface. It allows users to discover other peers on their network automatically and share files between them. The application uses both TCP for reliablebfile transfers and UDP for peer discovery, making it a hybrid networking solution.

### Core Classes
The application is structured around two main classes: P2PNodeGUI and P2PNode. The P2PNodeGUI class handles all user interface elements and interactions, while the P2PNode class manages the actual networking and file transfer operations. This separation makes the code more maintainable and easier to understand.

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
1. Run the application:
   ```
   python src/maingui.py
   ```
2. Enter the port number and click "Start Node".
3. Select a file to share and click "Send File".
