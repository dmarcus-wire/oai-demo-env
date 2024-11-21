# oai-demo-env

## Steps
```
oc login to cluster

# if ssh in and cloned
until oc apply -k demos/default ; do : ; done

# if not cloned
until oc apply -k https://github.com/dmarcus-wire/oai-demo-env.git ; do : ; done

# set the controller to not scheduleable in the web terminal
ocp_control_nodes_not_schedulable 
```

Attributes
1. Web Terminal
1. GPUs
1. NFD
1. NVIDIA GPU
1. DCGM Dashboard
1. RHOAI fast
    1. User
    1. Administrator
1. Minio
1. ACS
1. Power monitoring
1. Metering
1. Observability
    1. Cluster Observability Operator
    1. Power Monitoring
    1. Red Hat build of OpenTelemetry