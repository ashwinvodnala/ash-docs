# ash-docs

Purpose:
This document outlines the responsibilities of the Cloud Engineering team with respect to tagging and labeling of Google Cloud Platform (GCP) resources.

Scope of Responsibility:
The Cloud Engineering team is not responsible for the creation, maintenance, or updates of tags or labels on individual GCP resources beyond initial project setup.

Responsibilities include:

Creating GCP projects upon request.

Adding mandatory labels during project creation as per the organization’s standards.

If any required labels are inadvertently missed during project creation, we have implemented a GitHub Actions workflow that serves as a remediation process. This workflow allows us to update labels on GCP projects after creation, ensuring compliance with labeling standards.

Exclusions:

The Cloud Engineering team is not accountable for maintaining or updating labels/tags on GCP resources (e.g., Compute Engine instances, buckets, databases, etc.) beyond the project level.

For ongoing compliance, it is the responsibility of individual application or resource owners to ensure proper tagging on their GCP assets.



Audit Logs Streaming to Splunk – Architecture and Workflow Documentation

Overview
This document outlines the process implemented by the Cloud Engineering team to stream GCP audit logs to Splunk using a combination of Log Sinks, Pub/Sub, and a Dataflow job. The setup ensures centralized log collection and enables real-time visibility for security and operational monitoring.

Architecture Components
Log Sink (Organization Level)

A centralized log sink is created at the organization level.

The sink routes all audit logs to a Pub/Sub topic.

This setup ensures that logs from all projects within the organization are captured without the need to configure sinks at the individual project level.

Link to Log Sink Configuration:
[Insert Log Sink Link Here]

Pub/Sub Topic

The designated Pub/Sub topic acts as the buffer and transport layer for the streamed audit logs.

All audit log entries from the log sink are pushed to this topic in real time.

Dataflow Job

A Dataflow pipeline subscribes to the Pub/Sub topic and reads the incoming audit logs.

The job is responsible for formatting and forwarding the logs to Splunk
