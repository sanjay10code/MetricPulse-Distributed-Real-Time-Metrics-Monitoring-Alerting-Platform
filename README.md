# 📡 MetricPulse — Distributed Real-Time Metrics Monitoring

> A Grafana-style distributed metrics monitoring and alerting platform. Ingests 10,000+ metrics/sec via Apache Kafka, stores in InfluxDB, and streams live to a React-style dashboard via WebSocket.

![Kafka](https://img.shields.io/badge/Apache_Kafka-Ingestion-633806?style=for-the-badge&logo=apachekafka&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-Server-085041?style=for-the-badge&logo=nodedotjs&logoColor=white)
![InfluxDB](https://img.shields.io/badge/InfluxDB-TimeSeries-378ADD?style=for-the-badge)
![WebSocket](https://img.shields.io/badge/WebSocket-RealTime-3C3489?style=for-the-badge)

---

## ✨ Features

- **Apache Kafka ingestion** — high-throughput metrics pipeline, 10,000+ metrics/sec
- **Lightweight agents** — deployable on Linux/Windows with plugin interface
- **Grafana-style dashboard** — real-time charts for CPU, memory, requests, latency
- **Threshold-based alerting** — warn/critical levels with AWS SNS notifications
- **Anomaly detection** — automatic threshold breach detection
- **InfluxDB time-series** — optimized retention policies and downsampling
- **Demo mode** — runs fully with simulated hosts when no agents connected

---

## 🏗️ Architecture

```
Linux/Windows Agents
      │
      ▼ Apache Kafka (high throughput)
Ingestion Server (Node.js)
      │
      ├── InfluxDB (time-series storage)
      ├── Alerting Engine (threshold + anomaly)
      ├── AWS SNS (notifications)
      └── Socket.IO (real-time WebSocket)
              │
              ▼
      Dashboard (browser)
      CPU · Memory · Requests · Latency
```

---

## 🚀 How to Run

### 1. Clone the repo
```bash
git clone https://github.com/sanjay10code/MetricPulse
cd MetricPulse/metricpulse
```

### 2. Fix PowerShell policy (Windows only)
```powershell
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```

### 3. Start ingestion server
```bash
cd ingestion-server
npm install
node server.js
```
You should see:
```
[Server] MetricPulse ingestion server on port 3001
[Server] WebSocket agent listener on port 3002
```

### 4. Open the dashboard
Go to `dashboard/` folder and double-click `index.html`

Dashboard auto-connects to `localhost:3001` and shows live simulated metrics immediately.

### 5. Run a metric agent (optional)
Open a new terminal:
```bash
cd agent
npm install
node agent.js
```
Agent starts sending real CPU/memory/network metrics from your machine.

---

## 📁 Project Structure

```
metricpulse/
├── agent/
│   ├── agent.js            # Metric collection agent (plugin-based)
│   └── package.json
├── ingestion-server/
│   ├── server.js           # Kafka consumer + WebSocket + alerting
│   └── package.json
├── dashboard/
│   └── index.html          # Grafana-style real-time dashboard
└── README.md
```

---

## 📊 Metrics Collected

| Plugin | Metrics |
|--------|---------|
| CPU | usage %, cores, model |
| Memory | total, used, free, usage % |
| System | uptime, load avg 1m/5m/15m |
| Network | interfaces, primary IP |
| Custom App | req/sec, error rate, response time, connections |

---

## 🔐 Alert Thresholds

| Metric | Warning | Critical |
|--------|---------|----------|
| CPU usage | 70% | 90% |
| Memory usage | 75% | 90% |
| Error rate | 1% | 5% |
| Response time | 150ms | 500ms |

---

## 🛠️ Tech Stack

![JavaScript](https://img.shields.io/badge/JavaScript-0C447C?style=for-the-badge&logo=javascript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-085041?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Kafka](https://img.shields.io/badge/Apache_Kafka-633806?style=for-the-badge&logo=apachekafka&logoColor=white)
![InfluxDB](https://img.shields.io/badge/InfluxDB-378ADD?style=for-the-badge)
![Socket.io](https://img.shields.io/badge/Socket.io-085041?style=for-the-badge&logo=socketdotio&logoColor=white)
![Chart.js](https://img.shields.io/badge/Chart.js-3C3489?style=for-the-badge)
![AWS SNS](https://img.shields.io/badge/AWS_SNS-633806?style=for-the-badge&logo=amazonaws&logoColor=white)

