# Kubectl tips and tricks

## Kubectl 1.18 Changes

`Kubectl 1.18` came with a few breaking changes and deprecation you should be aware to not be caught by surprise during your exam.

### kubectl run

From version 1.18, only PODs are created using `kubectl run` command. `kubectl run` and `kubectl run --generator=deployment/v1beta1` are not valid to create deployments, jobs and cronjobs.



### --dry-run  
`--dry-run flag has been deprecated in favor or `--dry-run=client` or `--dry-run=server`.

### exec
`exec` has been deprecated and will be removed in future versions.

## kubectl Cheat Sheet

The kubernetes cheatsheet contains examples with most of the examples demonstrated here. For more examples, please chech on 
https://kubernetes.io/docs/reference/kubectl/cheatsheet/

## YAML generation
Use the flags `--dry-run=client` or `--dry-run=server` in conjunction with the `--output` (`-o`) flag to generate the output of the command without commiting the changes to k8s api. e.g:

```
kubectl run nginx --image=nginx --output=yaml --dry-run
```
Alternatively, get a resource and output as yaml
```
kubectl get pod nginx  --output=yaml --dry-run
```


## Undestand resources structure
Instead of decorate all yaml structure of each resource type, or searching in the docs the specific attribute you know exist but doesn't remember the exact name, to save you some time, you can output the structure of resource by using the explain command like below:

```
kubectl explain pods.spec.containers --recursive | less
```

## Create a Pod
```
kubectl run nginx --image=nginx 

kubectl run nginx --image=nginx \
    --requests "cpu=100m,memory=256Mi" \
    --limits "cpu=200m,memory=512Mi" 
```

## Create a deployment
```
kubectl create deployment nginx --image=nginx

# set resources, before creation
$ kubectl create deployment nginx --image=nginx --dry-run -o yaml > deploy.yaml
$ nano deploy.yaml      # set requests
$ kubectl apply -f deploy.yaml


# set resources, after creation
kubectl create deployment nginx --image=nginx
kubectl set resources deployment nginx -c=nginx \
  --requests=cpu=200m,memory=200Mi \
  --requests=cpu=200m,memory=200Mi
```

## Create a service
```
kubectl create service clusterip nginx --tcp=80
kubectl create service loadbalancer nginx --tcp=80 
kubectl create service nodeport nginx --tcp=80 
kubectl create service externalname my-ns --external-name bar.com

--tcp=<port>:<targetPort>
```
From existing deployment
```
kubectl expose deployment nginx --port=80 --target-port=80
```
From a new pod
```
kubectl run nginx --image=nginx --expose --port=80 --output=yaml --dry-run
```
## Create a Job

```
```

## Create a CronJob

```
```

## Edit a resource

    kubectl set 

    kubectl set image <resourceType> <resourceName> <container>=<image>

    # Set container 'app' to use image 'nginx:2' on pod nginx
    kubectl set image pod nginx app=nginx:2

    # Set a deployment's nginx container image to 'nginx:1.9.1', and its busybox container image to 'busybox'.
    kubectl set image deployment/nginx busybox=busybox nginx=nginx:1.9.1

    # Update all deployments' and rc's nginx container's image to 'nginx:1.9.1'
    kubectl set image deployments,rc nginx=nginx:1.9.1 --all

    # Update image of all containers of daemonset abc to 'nginx:1.9.1'
    kubectl set image daemonset abc *=nginx:1.9.1

    # Print result (in yaml format) of updating nginx container image from local file, without hitting the server
    kubectl set image -f path/to/file.yaml nginx=nginx:1.9.1 --local -o yaml

Editable Resources:

    env            Update environment variables on a pod template
    image          Update image of a pod template
    resources      Update resource requests/limits on objects with pod templates
    selector       Set the selector on a resource
    serviceaccount Update ServiceAccount of a resource
    subject        Update User, Group or ServiceAccount in a RoleBinding/ClusterRoleBinding

## Commands

    
    Usage:
        kubectl commands [options]

    Basic Commands (Beginner):  
    create        Create a resource from a file or from stdin.
    expose        Take a replication controller, service, deployment or pod and expose it as a new Kubernetes Service
    run           Run a particular image on the cluster
    set           Set specific features on objects

    Basic Commands (Intermediate):
    explain       Documentation of resources
    get           Display one or many resources
    edit          Edit a resource on the server
    delete        Delete resources by filenames, stdin, resources and names, or by resources and label selector

    Deploy Commands:
    rollout       Manage the rollout of a resource
    scale         Set a new size for a Deployment, ReplicaSet or Replication Controller
    autoscale     Auto-scale a Deployment, ReplicaSet, or ReplicationController

    Cluster Management Commands:
    certificate   Modify certificate resources.
    cluster-info  Display cluster info
    top           Display Resource (CPU/Memory/Storage) usage.
    cordon        Mark node as unschedulable
    uncordon      Mark node as schedulable
    drain         Drain node in preparation for maintenance
    taint         Update the taints on one or more nodes

    Troubleshooting and Debugging Commands:
    describe      Show details of a specific resource or group of resources
    logs          Print the logs for a container in a pod
    attach        Attach to a running container
    exec          Execute a command in a container
    port-forward  Forward one or more local ports to a pod
    proxy         Run a proxy to the Kubernetes API server
    cp            Copy files and directories to and from containers.
    auth          Inspect authorization

    Advanced Commands:
    diff          Diff live version against would-be applied version
    apply         Apply a configuration to a resource by filename or stdin
    patch         Update field(s) of a resource using strategic merge patch
    replace       Replace a resource by filename or stdin
    wait          Experimental: Wait for a specific condition on one or many resources.
    convert       Convert config files between different API versions
    kustomize     Build a kustomization target from a directory or a remote url.

    Settings Commands:
    label         Update the labels on a resource
    annotate      Update the annotations on a resource
    completion    Output shell completion code for the specified shell (bash or zsh)

    Other Commands:
    alpha         Commands for features in alpha
    api-resources Print the supported API resources on the server
    api-versions  Print the supported API versions on the server, in the form of "group/version"
    config        Modify kubeconfig files
    plugin        Provides utilities for interacting with plugins.
    version       Print the client and server version information
