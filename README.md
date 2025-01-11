# P2P File Sharing Application

## Overview
This project is a peer-to-peer file sharing application built using Python and Tkinter. It allows users to share files over a local network using a simple graphical user interface. By sarting nodes on devices in the network, a local peer-to-peer file sharing networking is set up. When sharing a file from one node, all nodes in the network will receive the file.

## Features
- Start a P2P nodes on devices in the network
- Select files to share to the netowrk
- Send files to other nodes

## Requirements
- Python 3.x
- Tkinter

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
