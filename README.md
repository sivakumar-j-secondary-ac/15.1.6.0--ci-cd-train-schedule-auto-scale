#Auto scale

```
git clone https://github.com/kubernetes-incubator/metrics-server.git
cd metrics-server/
git checkout ed0663b3b4ddbfab5afea166dfd68c677930d22e
kubectl create -f deploy/1.8+/
kubectl get --raw /apis/metrics.k8s.io/
cd ~/
git clone https://github.com/sivakumar-j-secondary-ac/cicd-pipeline-train-schedule-autoscaling.git
cd cicd-pipeline-train-schedule-autoscaling --make sure autoscale is updated in the yml file
kubectl apply -f train-schedule-kube.yml
```
#Increase the cpu load

```
kubectl run -i --tty load-generator --image=busybox /bin/sh
--once inside the container run the below once
while true; do wget -q -O- http://publicip/generate-cpu-load; done
```
