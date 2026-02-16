SDN-Shield: Real-Time DDoS Detection and Mitigation System
Prepared by:
Group 19 : DDoS Detection

Overview
A real-time DDoS (Distributed Denial of Service) detection and mitigation system built using Software-Defined Networking (SDN) principles. This system automatically detects flood attacks and blocks malicious traffic while maintaining service for legitimate users using the RYU SDN controller.

Components

Mininet - Network emulation environment
RYU Controller - SDN controller with custom DDoS detection logic
OpenFlow Switches - Programmable data plane
Custom Detection Algorithm - Real-time traffic analysis engine

Prerequisites

Ubuntu version: Ubuntu 20.04

sudo apt update
sudo apt install mininet python3-pip net-tools
pip3 install ryu

🚀 Running the System

Terminal 1: Start RYU Controller

cd ddos-detection-project
ryu-manager ddos_detector.py --verbose

Terminal 2: Start Network & Simulation

cd ddos-detection-project
sudo python3 Topology and simulation test.py

ddos-detection-project/
├── ddos_detector.py          # Main RYU controller logic
├── Topology and simulation test.py    # Complete simulation system
├── ddos_topo.py             # Network topology definition
└── README.md               # This file

How It Works:

1. Detection Algorithm

# Real-time packet rate monitoring
if packets_per_second > 30 
    trigger_mitigation(src_ip)

2. Traffic Analysis
Normal Traffic: < 30 PPS → 🟢 ALLOW

DDoS Attack: > 30 PPS → 🚨 BLOCK

3. Automatic Mitigation

Dynamic IP blacklisting
OpenFlow drop rule installation



