# sync-week-monitoring

Provide guidance for monitoring of Kubernetes and Kubernetes workloads on Azure.

# Topics

## Monitoring

### Prometheus and Grafana

- Install and Configure Prometheus
  - Helm 
  - Ansible Playbook (OpenShift)
- Install and Configure Grafana
  - Helm
  - Ansible Playbook (OpenShift)
- How to monitor the cluster monitoring
  - Kubernetes Cluster - Nodes, Pods
  - How Prometheus exposes
  - Does Prometheus capture resource events (i.e. crashbackoff, pod lifecycle, etc.)
- How to visualize your cluster
  - Dashboards - Prometheus marketplace
  - Basics
  - Advanced dashboards
- Alerting
   - Alert Manager
   - How about Pager Duty - Automate alerting
- How to monitor your app
   - Prometheus client SDK
   - Expose /metrics endpoint
   - How to configure for Prometheus to use (annotation, config)
- How to visualise your application monitoring
   - Dashboards
   - Setup metrics (i.e. counters, gauges, etc.)
   - How do you graph those?

### OMS

- Install and Configure OMS Agent
- How to monitor the cluster
- How to visualise your cluster monitoring
- Alerting
- How to monitor your app
- How to visualise your application monitoring

## Logs

### Fluentd

- Fluentbit
- Formatting and Aggregation (Server, fanout etc)

### EFK

*Installation (Helm)*

```bash
helm install incubator/elasticsearch
helm install incubator/fluentd-elasticsearch
helm install stable/kibana
# What values do we need to make this work well on Azure?
# Any extra config?
```

*TODO:*
- Installation (sidecar)
- Installation (sidecar - injected)
- Daemonset vs deployment?
- Verify collecting STDOUT/STDERR
- Verify collecting log file
- Verify collecting k8s custom metrics
- What logs we care about from the k8s cluster?
 - controllermanager
 - apiserver
 - kubelet
 - scheduler (ex: could not schedule because out of capacity)
- When do we aggregate? 
- How to configure capture of logs with a specific warning/error level? Can those get prioritized over INFO/DEBUG? Do those
- Alerting based on logs. Why do this vs metrics? Do we prefer metrics (probably?)?