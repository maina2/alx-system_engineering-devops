# 2-secured_and_monitored_web_infrastructure

## Diagram
(https://flic.kr/p/2rdeLCx)

## Infrastructure Specifics

### Additional Elements and Purpose
- **Firewall**: Filters network traffic to protect the server from unauthorized access and attacks. Added to secure the server by allowing only HTTP/HTTPS traffic (ports 80/443).
- **HTTPS (SSL/TLS)**: Encrypts browser-server communication. Added to ensure data privacy, integrity, and trust.
- **Monitoring Tool**: Tracks server performance (e.g., Prometheus). Added to detect issues and optimize resources.

### Explanations
- **Firewalls**: Block malicious traffic, allow specific ports (e.g., 80/443), and log suspicious activity to enhance security.
- **HTTPS**: Encrypts data to prevent interception, ensures data integrity, authenticates the server, and boosts user trust/SEO.
- **Monitoring**: Detects downtime, performance issues, and resource usage to ensure reliability and plan scalability.
- **Monitoring Data Collection**: A tool like Prometheus collects metrics (e.g., CPU, requests) via agents or exporters installed on the server, stored in a time-series database for analysis.
- **Monitoring QPS**: Configure Prometheus to scrape Nginx logs or metrics endpoint, count HTTP requests per second, and visualize QPS in a dashboard (e.g., Grafana).