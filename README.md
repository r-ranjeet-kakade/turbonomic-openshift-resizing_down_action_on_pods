# turbonomic-openshift-resizing_down_action_on_pods

This example creates a namespace on the RedHat OpenShift Platform with a deployment with 2 pod replicas. 

Each pod has 2 containers (an application container and a fake sidecar) and each container is underutilized for CPU and memory. 

Turbonomic will recommend resizing down actions for these resources.

## Creating a yaml for pod deployment.
```console
➜  oc create -f https://raw.githubusercontent.com/r-ranjeet-kakade/turbonomic-openshift-resizing_down_action_on_pods/main/pod_deployment.yaml
namespace/action-merge-test created
deployment.apps/action-merge-test created
```

This creates a namespace `action-merge-test` with a deployment `action-merge-test` with replicas=2. Each pod has 2 containers:

1. Container `cpu-mem-load` has following resources over-provisioned:
```yaml
resources:
  limits:
    memory: 200Mi
    cpu: 200m
  requests:
    memory: 130Mi
    cpu: 100m
```

2. Container `cpu-mem-load-test-sidecar` has following resources over-provisioned:
```yaml
resources:
  limits:
    memory: 200Mi
  requests:
    memory: 130Mi
```
