## Prerequisites

- Docker
- Docker Compose

## Quick Start

1. Start the monitoring stack:

```bash
docker-compose up -d
```

2. Verify all services are running:

```bash
docker-compose ps
```

## Accessing the Services

### Grafana

- **URL**: http://localhost:3000
- **Username**: `admin`
- **Password**: `admin`

### Prometheus

- **URL**: http://localhost:9090
- **Targets**: http://localhost:9090/targets (to verify node-exporter is being scraped)

### Node Exporter

- **URL**: http://localhost:9100/metrics
- Provides system metrics like CPU, memory, disk, and network statistics

## Configuration

### Grafana Setup

1. Log in to Grafana at http://localhost:3000
2. Add Prometheus as a data source:
   - Go to **Configuration** → **Data Sources** → **Add data source**
   - Select **Prometheus**
   - Set URL to: `http://prometheus:9090`
   - Click **Save & Test**

## Stopping the Stack

```bash
docker-compose down
```

To remove volumes as well:

```bash
docker-compose down -v
```

## Troubleshooting

Check logs for a specific service:

```bash
docker-compose logs prometheus
docker-compose logs node-exporter
docker-compose logs grafana
```

Check all logs:

```bash
docker-compose logs -f
```
