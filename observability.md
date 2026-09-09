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

## What is cAdvisor?

Node Exporter mainly monitors the host machine.
## But suppose you have multiple Docker containers:
You may want to know:

Which container is using high CPU?
Which container is consuming more memory?
How much network traffic is each container using?
How much disk I/O is each container generating?

👉 cAdvisor provides these container-level metrics.

cAdvisor (Container Advisor) is an open-source tool developed by Google that collects resource usage and performance metrics from running containers.

Simple definition:

cAdvisor monitors Docker containers and provides metrics about CPU, Memory, Network, and Disk usage.

Interview Answer 🎯

cAdvisor is a container monitoring tool that collects resource usage and performance metrics from running containers, such as CPU, memory, network, and filesystem usage. Prometheus scrapes these metrics from cAdvisor, and Grafana visualizes them in dashboards. Node Exporter monitors the host machine, while cAdvisor provides container-level monitoring.

## Log Monitoring

1. What is Loki?

Loki is a log aggregation system developed by Grafana Labs.

Simple definition:

Loki collects, stores, and allows you to query logs from applications and infrastructure.

Example logs:

INFO: Application started
INFO: Database connected
ERROR: Database connection failed
ERROR: API request failed

Loki stores these logs so you can view and search them in Grafana.

2. What is Promtail?

Promtail is a log collection agent.

Simple definition:

Promtail collects logs from containers or log files and sends them to Loki.

Application / Docker Container
           │
           │ Generates Logs
           ▼
        Promtail
           │
           │ Sends Logs
           ▼
          Loki
           │
           │ Stores Logs
           ▼
         Grafana
           │
           ▼
      View & Search Logs

Interview Answer 🎯

Loki is a log aggregation system used to collect, store, and query logs. Promtail acts as a log collection agent that reads logs from applications, servers, or containers and sends them to Loki. Grafana then connects to Loki to visualize and search the logs. Together, they provide centralized log monitoring and troubleshooting capabilities.