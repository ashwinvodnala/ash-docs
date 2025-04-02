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

