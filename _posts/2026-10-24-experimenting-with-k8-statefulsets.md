---
title: Experimenting with K8s StatefulSets by Building a Cloud Status Monitor
summary: Kubernetes, Kafka, Postgres
---

To keep feeding my curiosity about K8s StatefulSets, I came up with an architecture that lets me get more hands-on practice on my local machine at weekends.

## Architecture

![Cloud status monitor architecture]({{ '/assets/images/k8s-status-monitor-architecture.png' | relative_url }})

1. The **poller** service calls each cloud provider's status API every 60s and publishes the raw data to the `status.raw` Kafka topic.
2. The `status.raw` topic acts as a buffer between the poller and the processor. It keeps the raw data, so the processor can replay it even if it goes down.
3. The **processor** reads from `status.raw`, normalises the data, removes duplicates, and saves it in Postgres.
4. **Postgres** is the source of truth. It stores data about incidents, providers, and so on.
5. The **relay** service queries incident data from Postgres and publishes it to the `status.incidents` topic.
6. The **alerts** service reads from `status.incidents` and logs an alert-style message to the console.
7. The **dashboard** service queries only the data it needs to populate the dashboard.