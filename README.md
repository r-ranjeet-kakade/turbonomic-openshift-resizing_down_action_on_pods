# turbonomic-openshift-resizing_down_action_on_pods
This scenario creates a namespace with a deployment with 2 pod replicas. Each pod has 2 containers (an application container and a fake sidecar) and each container is underutilized for CPU and memory, where Turbo will recommend resizing down actions for these resources.
