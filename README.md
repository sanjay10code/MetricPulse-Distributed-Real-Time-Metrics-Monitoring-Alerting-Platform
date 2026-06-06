# MetricPulse-Distributed-Real-Time-Metrics-Monitoring-Alerting-Platform
•Designed and developed a distributed time-series metrics ingestion pipeline capable of handling high-throughput agent data streams using Apache Kafka and Node.js
•Built a Grafana-style React dashboard with real-time WebSocket updates visualizing CPU, memory, and custom application metrics across multiple hosts
•Implemented threshold-based and anomaly detection alerting engine with automated notifications via AWS SNS, reducing mean time to detect (MTTD) incidents
•Stored and queried time-series telemetry data using InfluxDB, optimizing retention policies and downsampling for long-term storage efficiency
•Developed lightweight metric collection agents deployable on Linux/Windows hosts, supporting custom metric instrumentation via a plugin interface
•Architected the system for horizontal scalability using Kafka consumer groups and stateless Node.js microservices, supporting 10,000+ metrics/sec ingestion
