## Monitoring and Observability

![monitoring_flow](https://storage.googleapis.com/github-repo/generative-ai/sample-apps/e2e-gen-ai-app-starter-pack/monitoring_flow.png)

### Trace and Log Capture

This application utilizes [OpenTelemetry](https://opentelemetry.io/) and [OpenLLMetry](https://github.com/traceloop/openllmetry) for comprehensive observability, emitting events to Google Cloud Trace and Google Cloud Logging. Every interaction with LangChain and VertexAI is instrumented (see [`server.py`](server.py)), enabling detailed tracing of request flows throughout the application.

Leveraging the [CloudTraceSpanExporter](https://cloud.google.com/python/docs/reference/spanner/latest/opentelemetry-tracing), the application captures and exports tracing data. To address the limitations of Cloud Trace ([256-byte attribute value limit](https://cloud.google.com/trace/docs/quotas#limits_on_spans)) and [Cloud Logging](https://cloud.google.com/logging/quotas) ([256KB log entry size](https://cloud.google.com/logging/quotas)), a custom extension of the CloudTraceSpanExporter is implemented in [`app/utils/tracing.py`](app/utils/tracing.py).

This extension enhances observability by:

- Creating a corresponding Google Cloud Logging entry for every captured event.
- Automatically storing event data in Google Cloud Storage when the payload exceeds 256KB.

Logged payloads are associated with the original trace, ensuring seamless access from the Cloud Trace console.

### Log Router

Events are forwarded to BigQuery through a [log router](https://cloud.google.com/logging/docs/routing/overview) for long-term storage and analysis. The deployment of the log router is done via Terraform code in [deployment/terraform](../deployment/terraform).

### Looker Studio Dashboard

Once the data is written to BigQuery, it can be used to populate a [Looker Studio dashboard](https://lookerstudio.google.com/c/reporting/fa742264-4b4b-4c56-81e6-a667dd0f853f/page/tEnnC).

This dashboard, offered as a template, provides a starting point for building custom visualizations on the top of the data being captured.