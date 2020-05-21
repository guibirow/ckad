https://medium.com/faun/be-fast-with-kubectl-1-18-ckad-cka-31be00acc443


https://www.youtube.com/watch?v=rnemKrveZks
```
kubectl run nginx --image=nginx   (deployment)

kubectl run nginx --image=nginx --restart=Never   (pod)

kubectl run nginx --image=nginx --restart=OnFailure   (job)  

kubectl run nginx --image=nginx  --restart=OnFailure --schedule="* * * * *" (cronJob)



kubectl run nginx -image=nginx --restart=Never --port=80 --namespace=myname --command --serviceaccount=mysa1 --env=HOSTNAME=local --labels=bu=finance,env=dev  --requests='cpu=100m,memory=256Mi' --limits='cpu=200m,memory=512Mi' --dry-run -o yaml - /bin/sh -c 'echo hello world'



kubectl run frontend --replicas=2 --labels=run=load-balancer-example --image=busybox  --port=8080

kubectl expose deployment frontend --type=NodePort --name=frontend-service --port=6262 --target-port=8080

kubectl set serviceaccount deployment frontend myuser

kubectl create service clusterip my-cs --tcp=5678:8080 --dry-run -o yaml


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
