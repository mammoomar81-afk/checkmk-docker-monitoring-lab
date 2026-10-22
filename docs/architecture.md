# System Architecture – Checkmk Docker Monitoring Lab

## Overview

This lab runs on Ubuntu Server 22.04.5 LTS in Oracle VirtualBox.
Checkmk monitors the Linux host, Docker services, and the Nginx web server.

## Network Configuration

| Interface | Purpose | IP address |
|---|---|---|
| enp0s3 | VirtualBox NAT | 10.0.2.15/24 |
| enp0s8 | VirtualBox Host-only | 192.168.10.10/24 |
| docker0 | Default Docker bridge | 172.17.0.1/16 (currently down) |
| Docker bridge | Docker Compose network | 172.18.0.1/16 |

## Architecture Diagram

```mermaid
flowchart TB
    Host["Windows Host"]
    VBox["Oracle VirtualBox"]
    Ubuntu["Ubuntu Server 22.04.5<br/>gate-monitor<br/>192.168.10.10"]
    Checkmk["Checkmk Community 2.5.0p14<br/>Web UI: Port 5000"]
    Docker["Docker Engine"]
    Nginx["Nginx Container<br/>Port 8080"]
    Browser["Web Browser / HTTP Check"]

    Host --> VBox
    VBox --> Ubuntu
    Ubuntu --> Checkmk
    Ubuntu --> Docker
    Docker --> Nginx
    Browser -->|HTTP| Nginx
    Checkmk -->|Monitors| Ubuntu
    Checkmk -->|Checks HTTP| Nginx
