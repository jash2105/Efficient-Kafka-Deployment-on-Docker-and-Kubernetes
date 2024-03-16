## Kafka Cluster Connection Guide

### Bootstrap Server Addresses

- **For remote client connections (external to the Docker host):** Use `localhost:29094`.
- **For connections from the Docker host:** Use `localhost:29092`.

### Monitoring Kafka with JMX Metrics

1. **JMX Metrics Endpoint:** `localhost:29103` - Access JMX metrics at this endpoint.
2. **Integrating JMX Exporter:**
   - Download the JMX Exporter JAR from [Prometheus JMX Exporter](https://github.com/prometheus/jmx_exporter).
   - To activate JMX metrics collection, ensure the JMX Exporter JAR is added and uncomment the "EXTRA_ARGS" line in your Kafka service configuration.

This approach simplifies the configuration details, making it easier for users to follow and implement the necessary steps for both secure communication and effective monitoring.