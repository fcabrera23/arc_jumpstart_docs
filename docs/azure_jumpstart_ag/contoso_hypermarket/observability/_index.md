---
type: docs
weight: 7
title: Observability
linkTitle: Observability
---

# Observability

## Overview

Infrastructure observability is essential for Contoso Hypermarket's to succeffully monitor and visualize the health of their Kubernetes and Arc-enabled Kubernetes environments. This enables them to proactively oversee the health and performance of their infrastructure, identify potential issues, and make data-driven decisions to optimize their operations. With infrastructure observability, Contoso ensures that their cloud and edge infrastructure remains reliable, efficient, and resilient, allowing them to deliver exceptional customer experiences.

[Prometheus](https://prometheus.io/) is a highly efficient open source monitoring system that collects and stores metrics from various sources in real-time. It offers a flexible query language for analyzing the collected metrics and offers robust alerting capabilities. [Grafana](https://grafana.com/) is a powerful open source data visualization and analytics platform. It allows users to create interactive and customizable dashboards to visualize the collected metrics in real-time.

By leveraging Prometheus and Grafana for infrastructure observability, Contoso enjoys several advantages. Firstly, Prometheus's efficient data collection ensures that Contoso can monitor crucial performance indicators and resource utilization in real-time. Secondly, Grafana provides a user-friendly interface for visualizing the collected metrics, enabling Contoso to create interactive and customizable dashboards. These dashboards enable valuable insights into their infrastructure’s health and performance, facilitate trend identification, and support informed decision-making. Lastly, the combination of Prometheus and Grafana supports troubleshooting and root cause analysis.

## Architecture

The observability infrastructure stack architecture leverages the [Kube Prometheus Stack](https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack). This stack is a collection of Kubernetes manifests, Grafana dashboards, and Prometheus rules that are used to set up and configure monitoring for Kubernetes clusters.

The manufacturing plants deploy Prometheus instances, which periodically scrape metrics from the AKS edge essentials cluster. A Grafana instance is set up separately to centralize monitoring and visualization. The Prometheus instances send their metrics data to this central Grafana instance. Grafana dashboards are configured to display relevant metrics, allowing operators and administrators to monitor the health and performance of the entire infrastructure.

![Screenshot showing Observability infrastructure stack architecture](./img/observability_technology_stack.png)

## Grafana dashboards

Grafana's dashboards in Contoso's implementation provide a visually appealing and customizable interface for monitoring their infrastructure. With Grafana, they can create intuitive and interactive dashboards that display key metrics and insights, empowering them to make data-driven decisions and quickly identify any issues or trends within their cloud to edge infrastructure. The following Grafana dashboards are automatically deployed as part of advanced automation for all the manufacturing plants:

- **Kubernetes / Views / Global**: The Kubernetes Global Dashboard in Grafana offers a concise overview of your Kubernetes cluster, allowing you to quickly assess its overall health and performance. The dashboard includes panels that highlight key metrics, such as total cluster CPU, RAM, and network utilization, as well as resource usage across namespaces and nodes. Additionally, it tracks the number of resource types used in the cluster and helps detect misconfigured application resources by comparing real usage with requested and limited resources.

- **Node Exporter Full**: The Kubernetes Nodes Dashboard in Grafana provides a detailed view of node-level metrics and resources in your Kubernetes cluster. It enables you to monitor CPU and RAM usage, track pods running on each node, and identify any resource anomalies or performance issues. The dashboard also offers system-level metrics such as system load, context switches, and file descriptors, allowing for troubleshooting and optimization. Additionally, it provides insights into storage capacity, volumes, and I/O operations on the nodes, aiding in the effective management of storage resources.