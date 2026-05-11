# Bash System Health Monitor

A lightweight Linux system monitoring utility written in Bash that checks CPU, memory, disk usage, running services, and listening ports.

Designed to simulate the kind of operational monitoring and automation commonly used in real DevOps and Linux server environments.

---

## Why This Project Exists

Production servers can fail silently due to:

- High CPU usage
- Memory exhaustion
- Full disks
- Stopped services
- Closed or unavailable ports

This project automates basic health checks and provides structured logging and alert-style output to help detect issues early.

The script is designed with a real operational mindset:
- automated execution via cron
- threshold-based alerting
- structured logs
- defensive scripting
- clear exit codes

---

## Features

- CPU usage monitoring
- Memory usage monitoring
- Disk usage checks for mounted filesystems
- Service health checks
- Port availability checks
- Structured logging with timestamps
- INFO / WARN / ERROR / DEBUG log levels
- Colored terminal output
- Verbose mode support
- Daily rotating log files
- Cron automation support
- Cleanup handling using `trap`
- Threshold-based alert reporting

---

## Technologies & Tools Used

- `Bash`
- `awk`
- `cron`
- `getopts`
- `trap`
- `top`
- `free`
- `df`
- `ss`
- `pgrep`
- `systemctl`

---

## Project Structure

```bash
bash-system-health-monitor/
├── health-monitor.sh
├── logs/
├── screenshots/
└── README.md
```

---

## How It Works

The script follows a basic monitoring workflow:

1. Collect system metrics using Linux utilities
2. Parse values using `awk`
3. Compare metrics against configured thresholds
4. Generate alerts when limits are exceeded
5. Write structured logs with timestamps
6. Return proper exit codes for automation systems

---

## Usage

### Make script executable

```bash
chmod +x health-monitor.sh
```

### Run manually

```bash
./health-monitor.sh
```

### Run in verbose mode

```bash
./health-monitor.sh -v
```

### Use custom log file

```bash
./health-monitor.sh -l /tmp/custom.log
```

---

## Example Cron Automation

Run every 5 minutes:

```bash
*/5 * * * * /path/to/health-monitor.sh >> /path/to/logs/cron.log 2>&1
```

---

## Example Checks Performed

### CPU
- Detects high CPU utilization

### Memory
- Calculates used memory percentage

### Disk
- Monitors mounted filesystem usage

### Services
- Verifies critical services are running

### Ports
- Checks whether expected ports are listening

---

## Logging Example

```text
[2026-05-11 10:15:01] [INFO] CPU usage OK: 22%
[2026-05-11 10:15:01] [WARN] Disk HIGH on /: 85%
[2026-05-11 10:15:02] [INFO] Service running: ssh
```

---

## Skills Demonstrated

- Linux system monitoring
- Bash scripting
- Structured logging
- Cron automation
- Defensive scripting
- Metrics parsing with `awk`
- Exit code handling
- Process and service validation
- Operational troubleshooting mindset

---

## Future Improvements

- Email or Slack alert integration
- Docker container monitoring
- Network connectivity checks
- JSON log output
- Config file support
- Multi-server monitoring support

---

## Screenshots

Added screenshots showing:
- [Script execution & Output](screenshots/Script-execution.png)
- [Output in cron log file](screenshots/Cron-log-output.png)
- [Generated logs](screenshots/Generated-logs.png)
- [Cron configuration](screenshots/Cron-configuration.png)

---

## What This Project Demonstrates

This project demonstrates the ability to build production-style operational automation scripts using core Linux and Bash tooling.

It reflects practical DevOps fundamentals including:
- observability
- automation
- monitoring
- alerting
- logging
- defensive scripting

These are foundational skills used daily in real infrastructure and operations environments.
