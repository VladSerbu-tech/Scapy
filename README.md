Port Scanner

This repository contains a Python script for scanning open TCP ports on a target IP address. The script uses the scapy library to craft and send network packets, implementing a basic SYN scan to determine which ports are open.

Features

Sends SYN packets to a range of ports on a target IP.

Detects open ports by analyzing SYN-ACK responses.

Sends RST packets to gracefully close connections for identified open ports.

Scans the first 1024 common TCP ports by default.

How It Works

SYN Packet Transmission: The script sends a TCP SYN packet to each specified port on the target IP.

Response Analysis: If the target responds with a SYN-ACK packet, the port is marked as open.

Connection Closure: An RST packet is sent to close the connection after identifying an open port.

Result Compilation: All open ports are stored in a list and displayed to the user after the scan is complete.

Prerequisites

Python 3.6 or higher

scapy library installed

Installation

Clone this repository and navigate to the project directory:

git clone <repository-url>
cd <repository-directory>

Install the required library:

pip install scapy

Usage

Run the script using Python:

python port_scanner.py

Example Output

Enter the target IP: 192.168.1.1
Scanning 192.168.1.1 for open ports...
Open ports found: [22, 80, 443]

Script Breakdown

scan_ports Function

Input:

target (string): Target IP address to scan.

ports (iterable): Range of port numbers to scan.

Output:

open_ports (list): List of open ports.

Logic:

For each port in the specified range, a TCP SYN packet is sent.

Responses are analyzed to identify open ports (those that reply with SYN-ACK).

RST packets are sent to terminate connections gracefully.

Main Program

Accepts user input for the target IP.

Scans ports 1 through 1024 by default.

Prints a summary of open ports, if any.

Disclaimer

This script is intended for educational purposes only. Unauthorized port scanning can be illegal and is strictly prohibited without explicit permission from the network owner.

Contribution

Feel free to fork this repository and contribute to enhance the functionality of the script. Pull requests are welcome.
