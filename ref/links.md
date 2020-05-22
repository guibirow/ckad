https://medium.com/faun/be-fast-with-kubectl-1-18-ckad-cka-31be00acc443

https://codeburst.io/the-ckad-browser-terminal-10fab2e8122e
https://codeburst.io/kubernetes-ckad-weekly-challenges-overview-and-tips-7282b36a2681


https://www.katacoda.com/ckad-prep/scenarios/first-steps
https://www.katacoda.com/fabito/scenarios/ckad

# Notes

https://medium.com/chotot/tips-tricks-to-pass-certified-kubernetes-application-developer-ckad-exam-67c9e1b32e6e

On the [CKAD exercise(https://github.com/dgkanatsios/CKAD-exercises)], it misses two parts includes network policy and logging architect. But it takes 15% of your score so it’s very important to finish.

- Network policy question: On my exam, this is a troubleshooting problem. The pod cannot access service because of created network policy. So you might describe network policy then the correct label of the pods to fix it. If you understand the network policy, very quickly to finish the problem. Read more the task [Declare Network Policy](https://kubernetes.io/docs/tasks/administer-cluster/declare-network-policy/).

- Logging architecture k8s: You should understand cluster-level-logging. Read [Logging Architecture](https://kubernetes.io/docs/concepts/cluster-administration/logging/), especially [Sidecar container](https://kubernetes.io/docs/concepts/cluster-administration/logging/#sidecar-container-with-a-logging-agent) with a logging agent to understand sidecar container, fluentd.

# OUTDATED scripts
https://www.youtube.com/watch?v=rnemKrveZks
```

kubectl run nginx -image=nginx --restart=Never --port=80 --namespace=myname --command --serviceaccount=mysa1 --env=HOSTNAME=local --labels=bu=finance,env=dev  --requests='cpu=100m,memory=256Mi' --limits='cpu=200m,memory=512Mi' --dry-run -o yaml - /bin/sh -c 'echo hello world'


kubectl expose deployment frontend --type=NodePort --name=frontend-service --port=6262 --target-port=8080

kubectl set serviceaccount deployment frontend myuser

kubectl create service clusterip my-cs --tcp=5678:8080 --dry-run -o yaml


#######################################
### THE BELOW SNIPPETS ARE OUTDATED ###
#######################################

kubectl run nginx --image=nginx   (deployment) deprecated

kubectl run nginx --image=nginx --restart=Never   (pod)

kubectl run nginx --image=nginx --restart=OnFailure   (job)  

kubectl run nginx --image=nginx  --restart=OnFailure --schedule="* * * * *" (cronJob)

kubectl run frontend --replicas=2 --labels=run=load-balancer-example --image=busybox  --port=8080


Unix bash on-liners: 

args: ["-c", "while true; do date >> /var/log/app.txt; sleep 5;done"]

args: [/bin/sh, -c,'i=0; while true; do echo "$i: $(date)"; i=$((i+1)); sleep 1; done’]

args: ["-c", "mkdir -p collect; while true; do cat /var/data/* > /collect/data.txt; sleep 10; done"]



a=10;b=5; if [ $a -le $b ]; then echo "a is small" ; else echo "b is small"; fi

x=1; while [ $x -le 10 ]; do echo "welcome $x times"; x=$((x+1)); done



Use of GREP: 

Kubectl describe pods | grep --context=10 annotations:

Kubectl describe pods | grep --context=10 Events:
```
