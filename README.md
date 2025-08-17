# Monitoring System Performance with Netdata

## Overview
This project demonstrates the installation and usage of **Netdata**, a powerful, open-source monitoring tool, to visualize system and application performance metrics such as CPU, memory, and disk usage. Running Netdata in a Docker container allows for real-time monitoring of system resources, providing valuable insights into performance and resource utilization.

Monitoring system resources is crucial for ensuring reliability, optimizing performance, and quickly diagnosing potential issues in development or production environments. By using Netdata, we can gain a detailed understanding of their infrastructure at a glance.

## Tools Used
- **Netdata**: Open-source system and application performance monitoring tool.
- **Docker**: Containerization platform used to run Netdata.
- **GitHub Codespaces**: Cloud-based development environment hosting the Docker container.

## Solution and Steps
To run Netdata successfully and access the full system metrics in a Codespaces environment, use the following command:

```bash
docker run -d --name=netdata -p 19999:19999 --privileged --pid=host netdata/netdata
```

### Explanation of Key Flags
- `--privileged`: Grants the container extended permissions to access host resources.
- `--pid=host`: Allows the container to see and monitor host system processes.
- `-p 19999:19999`: Maps the Netdata dashboard to the host port 19999 for easy browser access.

## Debugging and Troubleshooting

### 1. Container Name Conflict
- **Issue**: Error stating the container name `netdata` was already in use.
- **Solution**: Remove the existing container:
```bash
docker stop netdata
docker rm netdata
```

### 2. Dashboard Initially Empty
- **Issue**: Dashboard loaded but no metrics were visible.
- **Reason**: The container couldn’t access host system metrics.
- **Solution**: Added `--privileged` and `--pid=host` flags to grant proper access.

### 3. Metrics Display Issues
- **Issue**: Initially, only some metrics were visible.
- **Solution**: Adjusted container configuration to ensure all relevant system metrics, including CPU, memory, and disk usage, were properly displayed.

## Deliverables

### 1. Metrics Overview Screenshot
![Metrics Overview](<img width="1366" height="768" alt="Screenshot (13)" src="https://github.com/user-attachments/assets/9b46e152-1075-49ad-b9ae-a89f803dff37" />
)
*Shows key system metrics, including CPU, memory, and disk usage, highlighting Netdata’s real-time monitoring functionality.*

### 2. Full Dashboard Screenshot
![Full Dashboard](<img width="1366" height="768" alt="Screenshot (12)" src="https://github.com/user-attachments/assets/e81c4c58-325c-4544-96fc-acfa9fff7373" />
)
*Displays the complete Netdata dashboard with all metrics fully populated, demonstrating the effectiveness of the monitoring setup.*

## Importance of System Monitoring
Monitoring system resources is essential for:
- **Performance Optimization**: Identify bottlenecks and improve application efficiency.
- **Proactive Troubleshooting**: Detect issues before they escalate into critical failures.
- **Resource Management**: Make informed decisions on scaling and resource allocation.

By completing this setup, you gain practical experience with containerized monitoring solutions and improve your ability to manage and optimize system performance in real-world environments.
