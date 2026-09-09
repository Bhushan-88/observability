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

## What is Grafana?

Grafana is an open-source visualization and monitoring tool used to display data from different data sources in dashboards.

In simple words:

Grafana converts monitoring data into beautiful graphs, charts, gauges, and dashboards.

Why do we use Grafana?

Suppose Node Exporter collects these metrics:

CPU Usage
Memory Usage
Disk Usage
Network Traffic
System Load

Prometheus stores these metrics, but Grafana helps you visualize and monitor them easily.

- Architecture
Node Exporter
     ↓
Collects System Metrics
     ↓
Prometheus
     ↓
Stores Metrics
     ↓
Grafana
     ↓
Visualizes Data

Interview Answer 🎯

Grafana is an open-source monitoring and observability platform used to visualize and analyze metrics, logs, and traces. It connects with data sources such as Prometheus and displays the collected data using dashboards, graphs, charts, and gauges. Grafana also supports alerting, helping DevOps teams monitor infrastructure and applications and quickly identify issues.

## 