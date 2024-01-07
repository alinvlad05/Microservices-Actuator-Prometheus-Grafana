# Microservices-Actuator-Prometheus-Grafana
 
# Application Monitoring with Metrics

To properly monitor, manage, and troubleshoot an application running in production, we need to be able to answer questions like:

- "How much CPU and RAM is the application consuming?"
- "How many threads are used over time?"
- "What's the rate of failing requests?"

Event logs and health probes can't help us answer those questions. We need something more. We need more data.

Metrics are numeric data about the application, measured and aggregated in regular time intervals. We use metrics to:

- Track the occurrence of an event (such as an HTTP request being received).
- Count items (such as the number of allocated JVM threads).
- Measure the time taken to perform a task (such as the latency of a database query).
- Get the current value of a resource (such as current CPU and RAM consumption). This is all valuable information for understanding why an application behaves in a certain way. You can monitor metrics and set alerts or notifications for them.

Spring Boot Actuator collects application metrics out of the box by leveraging the Micrometer library (https://micrometer.io). Micrometer contains instrumentation code for collecting valuable metrics from common components in a JVM-based application. It provides a vendor-neutral façade so that you can export the metrics collected from Micrometer using different formats, such as Prometheus/Open Metrics, Humio, Datadog, and VMware Tanzu Observability. Just as SLF4J provides a vendor-neutral façade for logging libraries, Micrometer does the same for metrics exporters.

On top of the default Micrometer instrumentation libraries that are configured by Spring Boot, you can import additional instrumentation to collect metrics from specific libraries like Resilience4J or even define your own without vendor lock-in.

The most common format for exporting metrics is the one used by Prometheus, which is "an open-source systems monitoring and alerting toolkit" (https://prometheus.io). Just as Loki aggregates and stores event logs, Prometheus does the same with metrics.
