# Real-Time System Monitoring with Netdata

## Overview
This project demonstrates the installation and configuration of **Netdata**, an open-source, real-time monitoring tool, to track system and application performance metrics, including CPU, memory, and disk usage. Running Netdata in a Docker container enables developers to visualize resource usage and quickly identify bottlenecks.

> **Challenge:** In a resource-constrained environment (GitHub Codespaces), the standard Netdata dashboard rendered but displayed **only a single line**, making it unusable.  
> **Solution:** A **lite version** of the dashboard was created to ensure full visibility of key metrics while maintaining performance.

Monitoring system resources is essential for reliability, performance optimization, and proactive troubleshooting in both development and production environments.

---

## Tools Used
- **Netdata** – Open-source system and application performance monitoring.  
- **Docker** – Containerization platform to run Netdata.  
- **GitHub Codespaces** – Cloud-based development environment hosting the container.  

---

## Implementation Steps

### Running Netdata
Use the following command to run Netdata with full host system access:

```bash
docker run -d --name=netdata -p 19999:19999 --privileged --pid=host netdata/netdata
```

**Key Flags Explained:**
- `--privileged` → Grants extended permissions to access host resources.  
- `--pid=host` → Enables monitoring of host processes.  
- `-p 19999:19999` → Maps the dashboard to the host port for browser access.  

### Lite Dashboard Configuration
- **Problem:** Full dashboard rendered but only showed a single line due to Codespaces’ resource constraints.  
- **Solution:** Configured a **lite version of the dashboard**, ensuring it rendered correctly while displaying all essential metrics (CPU, memory, disk).  
- **Impact:** Achieved a fully functional, lightweight monitoring dashboard that could run reliably in a constrained environment.

---

## Debugging & Troubleshooting

### 1. Container Name Conflict
- **Issue:** Error: container name `netdata` already in use.  
- **Solution:** Remove existing container:
```bash
docker stop netdata
docker rm netdata
```

### 2. Empty Dashboard
- **Issue:** Dashboard loaded but no metrics were visible.  
- **Reason:** Container lacked access to host system metrics.  
- **Solution:** Added `--privileged` and `--pid=host` flags.

### 3. Single-Line Dashboard
- **Issue:** Full dashboard rendered only as a single line, making it unusable.  
- **Solution:** Created a **lite version** for proper rendering and visualization of all metrics.

---

## Deliverables

### 1. Lite v Dashboard Screenshot

<img width="1366" height="768" alt="Screenshot (12)" src="https://github.com/user-attachments/assets/48dfed6e-dbd3-4b0b-a6bc-75558aeae6c6" />


*This Shows the fully functional lite dashboard with all key metrics populated, including CPU, memory, and disk usage.*


### 2. Metrics Overview Screenshot

<img width="1366" height="768" alt="Screenshot (13)" src="https://github.com/user-attachments/assets/dd414320-4f34-4423-901d-8f4ec43e9fbb" />


*This *Shows key system metrics, including CPU, memory, and disk usage etc.*

---

## Importance of System Monitoring
Monitoring system resources is critical for:
- **Performance Optimization** – Identify bottlenecks and optimize resource usage.  
- **Proactive Troubleshooting** – Detect and resolve issues before they escalate.  
- **Resource Management** – Make informed scaling and infrastructure decisions.  

