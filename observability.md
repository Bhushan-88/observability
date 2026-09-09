# Observability is the ability to understand the internal state of an application or system by analyzing its external outputs, such as metrics, logs, and traces.

Simple Definition 🎯

Observability helps DevOps teams understand what is happening inside an application or infrastructure without directly accessing every component.

## Three Pillars of Observability
Metrics 📊
Numerical data about system performance.
CPU usage
Memory usage
Request count
Response time

Logs 📄
Detailed records of events happening in the system.

User login successful
Database connection failed
Application error occurred

Traces 🔍
Track a request as it travels through multiple services.

Example:

User → Frontend → API → Backend → Database

- Suppose your application is slow:

Metrics show high CPU usage.
Logs show database connection errors.
Traces show the request is taking too long in the database.

        Docker Host
            │
            ▼
    ┌───────────────┐
    │   Prometheus  │
    │   Container   │
    └───────┬───────┘
            │ Scrapes Metrics
            ▼
    ┌───────────────┐
    │ Node Exporter │
    │   Container   │
    └───────────────┘
            │
            ▼
     Host System Metrics
    CPU | RAM | Disk | Network

1. Node Exporter

Node Exporter collects system-level metrics such as:

CPU usage
Memory usage
Disk usage
Network statistics
System load

It exposes metrics, usually on:
http://localhost:9100/metrics

2. Prometheus
Prometheus connects to Node Exporter and scrapes (collects) the metrics periodically.

Usually Prometheus runs on:
http://localhost:9090

## Interview Answer 💡
Observability in DevOps is the capability to monitor and understand the internal behavior and health of applications and infrastructure using metrics, logs, and traces. It helps teams quickly detect issues, troubleshoot problems, identify root causes, and improve system reliability and performance.

