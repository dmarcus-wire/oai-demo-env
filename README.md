# oai-demo-env

1. provision OCP cluser
2. create dir structure to install Web Terminal Operator
3. oc apply -k components/web-terminal 
subscription.operators.coreos.com/web-terminal created
devworkspacetemplate.workspace.devfile.io/web-terminal-tooling created
4. create dir structure to install RHOAI Operator
oc apply -k components/rhoai-ready 
namespace/nvidia-gpu-operator created
namespace/openshift-nfd created
namespace/openshift-serverless created
namespace/redhat-ods-applications created
namespace/redhat-ods-monitoring created
namespace/redhat-ods-operator created
namespace/rhods-notebooks created
serviceaccount/job-aws-gpu-machineset created
serviceaccount/job-gpu-console-plugin created
serviceaccount/job-setup-machineset created
serviceaccount/job-pipelines-console-plugin created
serviceaccount/fix-dashboard-magic created
serviceaccount/approve-after-servicemesh created
serviceaccount/wait-for-servicemesh created
role.rbac.authorization.k8s.io/fix-dashboard-magic created
clusterrole.rbac.authorization.k8s.io/approve-after-servicemesh created
clusterrole.rbac.authorization.k8s.io/job-aws-gpu-machineset created
clusterrole.rbac.authorization.k8s.io/job-gpu-console-plugin created
clusterrole.rbac.authorization.k8s.io/job-pipelines-console-plugin created
clusterrole.rbac.authorization.k8s.io/job-setup-machineset created
clusterrole.rbac.authorization.k8s.io/wait-for-servicemesh created
rolebinding.rbac.authorization.k8s.io/fix-dashboard-magic created
clusterrolebinding.rbac.authorization.k8s.io/approve-after-servicemesh created
clusterrolebinding.rbac.authorization.k8s.io/fix-rhoai-kubeadmin created
clusterrolebinding.rbac.authorization.k8s.io/job-aws-gpu-machineset created
clusterrolebinding.rbac.authorization.k8s.io/job-gpu-console-plugin created
clusterrolebinding.rbac.authorization.k8s.io/job-pipelines-console-plugin created
clusterrolebinding.rbac.authorization.k8s.io/job-setup-machineset created
clusterrolebinding.rbac.authorization.k8s.io/wait-for-servicemesh created
configmap/console-plugin-nvidia-gpu created
configmap/device-plugin-config created
configmap/job-aws-gpu-machineset created
configmap/job-gpu-console-plugin created
configmap/nvidia-dcgm-exporter-dashboard created
configmap/job-setup-machineset created
configmap/job-pipelines-console-plugin created
configmap/fix-dashboard-magic created
configmap/notebook-controller-culler-config created
configmap/odh-segment-key-config created
configmap/approve-after-servicemesh created
configmap/wait-for-servicemesh created
service/console-plugin-nvidia-gpu created
deployment.apps/console-plugin-nvidia-gpu created
Warning: GPU accelerator label contains a poorly formed value: nvidia.com/gpu, errors: a valid label must be an empty string or consist of alphanumeric characters, '-', '_' or '.', and must start and end with an alphanumeric character (e.g. 'MyValue',  or 'my_value',  or '12345', regex used for validation is '(([A-Za-z0-9][-A-Za-z0-9_.]*)?[A-Za-z0-9])?'). This is not an error but may cause issues when using GPU resource limits with the Cluster Autoscaler. For more information on the proper use of these values, please see https://access.redhat.com/solutions/6055181
Warning: GPU accelerator label contains a poorly formed value: amd.com/gpu, errors: a valid label must be an empty string or consist of alphanumeric characters, '-', '_' or '.', and must start and end with an alphanumeric character (e.g. 'MyValue',  or 'my_value',  or '12345', regex used for validation is '(([A-Za-z0-9][-A-Za-z0-9_.]*)?[A-Za-z0-9])?'). This is not an error but may cause issues when using GPU resource limits with the Cluster Autoscaler. For more information on the proper use of these values, please see https://access.redhat.com/solutions/6055181
clusterautoscaler.autoscaling.openshift.io/default created
job.batch/job-aws-gpu-machineset created
job.batch/job-gpu-console-plugin created
job.batch/job-setup-machineset created
job.batch/job-pipelines-console-plugin created
job.batch/fix-dashboard-magic created
job.batch/approve-after-servicemesh created
job.batch/wait-for-servicemesh created
consolelink.console.openshift.io/github-catalog created
consolelink.console.openshift.io/github-ssa created
consolelink.console.openshift.io/help-link created
consolenotification.console.openshift.io/banner-cluster created
consolenotification.console.openshift.io/banner-demo created
consoleplugin.console.openshift.io/console-plugin-nvidia-gpu created
acceleratorprofile.dashboard.opendatahub.io/nvidia created
datasciencecluster.datasciencecluster.opendatahub.io/default-dsc created
dscinitialization.dscinitialization.opendatahub.io/default-dsci created
nodefeaturediscovery.nfd.openshift.io/nfd-instance created
clusterpolicy.nvidia.com/gpu-cluster-policy created
odhdashboardconfig.opendatahub.io/odh-dashboard-config created
operatorgroup.operators.coreos.com/gpu-operator-certified created
operatorgroup.operators.coreos.com/nfd created
operatorgroup.operators.coreos.com/serverless-operator created
operatorgroup.operators.coreos.com/rhods-operator created
subscription.operators.coreos.com/gpu-operator-certified created
subscription.operators.coreos.com/nfd created
subscription.operators.coreos.com/authorino-operator created
subscription.operators.coreos.com/openshift-pipelines-operator-rh created
subscription.operators.coreos.com/servicemeshoperator created
subscription.operators.coreos.com/serverless-operator created
subscription.operators.coreos.com/rhods-operator created
template.template.openshift.io/trition-serving-runtime created 
