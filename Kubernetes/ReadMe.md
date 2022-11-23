## Kuberentes Architecture

```meramid
graph TD;
    Cluster --> Master-Node(Manages-cluster);
    Cluster --> Worker-Node(Run Application);
```

```meramid
graph TD;
    Master-Node --> API Server(Kube-apiserver);
    Master-Node --> Distribute-Database(etcd);
    Master-Node --> Scheduler(kube-scheduler);
    Master-Node --> Control-Manager(Kube-controller-manager);
```

```meramid
graph TD;
    Worker-Node --> Node-Agent(Kubelet);
    Worker-Node --> Networking-Component(Kube-Proxy);
    Worker-Node --> Container-Runtime(RI-docker..etc);
    Worker-Node --> Pods(Multiple-pods-running-containers);
```

```meramid
graph TD;
    Worker-Node --> Pod1;
    Worker-Node --> Pod2;
    Pod1 --> Container1;
    Pod1 --> Container2;
    Pod2 --> Container3;
    Pod2 --> Container4;
```

## Kuberenetes setup

Here is the document or blog to set up kuberenetes. Please click on this [link](https://nikhilgowda.pythonanywhere.com/blog/1/).

### Kubernetes dashboard-setup

Here is the link or blog to setup dashboard. [Click here](https://nikhilgowda.pythonanywhere.com/blog/4/)

### Kuberenetes create namespace and services

Here is the blog for it. [Press here](https://nikhilgowda.pythonanywhere.com/blog/5/)

### Kuberenets Deployment architecture

```meramid
graph TD;
    Deployment --> Replica-Set1;
    Deployment --> Replica-Set2;
    Replica-Set1 --> Pod-Instance1;
    Replica-Set1 --> Pod-Instance2;
    Replica-Set2 --> Pod-Instance3;
    Replica-Set2 --> Pod-Instance4;
```

## Kuberentes Commands

```bash

docker run -p 8080:8080 home/hello-world-rest-api:0.0.1.RELEASE

kubectl create deployment hello-world-rest-api --image=home/hello-world-rest-api:0.0.1.RELEASE
kubectl expose deployment hello-world-rest-api --type=LoadBalancer --port=8080
kubectl scale deployment hello-world-rest-api --replicas=3
kubectl delete pod hello-world-rest-api-58ff5dd898-62l9d
kubectl autoscale deployment hello-world-rest-api --max=10 --cpu-percent=70
kubectl edit deployment hello-world-rest-api #minReadySeconds: 15
kubectl set image deployment hello-world-rest-api hello-world-rest-api=home/hello-world-rest-api:0.0.2.RELEASE


kubectl create deployment hello-world-rest-api --image=home/hello-world-rest-api:0.0.1.RELEASE
kubectl expose deployment hello-world-rest-api --type=LoadBalancer --port=8080
kubectl set image deployment hello-world-rest-api hello-world-rest-api=DUMMY_IMAGE:TEST
kubectl get events --sort-by=.metadata.creationTimestamp
kubectl set image deployment hello-world-rest-api hello-world-rest-api=home/hello-world-rest-api:0.0.2.RELEASE
kubectl get events --sort-by=.metadata.creationTimestamp
kubectl get componentstatuses
kubectl get pods --all-namespaces

kubectl get events
kubectl get pods
kubectl get replicaset
kubectl get deployment
kubectl get service

kubectl get pods -o wide

kubectl explain pods
kubectl get pods -o wide

kubectl describe pod hello-world-rest-api-58ff5dd898-9trh2

kubectl get replicasets
kubectl get replicaset

kubectl scale deployment hello-world-rest-api --replicas=3
kubectl get pods
kubectl get replicaset
kubectl get events
kubectl get events --sort-by=.metadata.creationTimestamp

kubectl get rs
kubectl get rs -o wide
kubectl set image deployment hello-world-rest-api hello-world-rest-api=DUMMY_IMAGE:TEST
kubectl get rs -o wide
kubectl get pods
kubectl describe pod hello-world-rest-api-85995ddd5c-msjsm
kubectl get events --sort-by=.metadata.creationTimestamp

kubectl set image deployment hello-world-rest-api hello-world-rest-api=home/hello-world-rest-api:0.0.2.RELEASE
kubectl get events --sort-by=.metadata.creationTimestamp
kubectl get pods -o wide
kubectl delete pod hello-world-rest-api-67c79fd44f-n6c7l
kubectl get pods -o wide
kubectl delete pod hello-world-rest-api-67c79fd44f-8bhdt

kubectl get componentstatuses
kubectl get pods --all-namespaces

kubectl version
gcloud container clusters get-credentials homeutes-cluster --zone us-central1-a --project solid-course-258105

kubectl rollout history deployment hello-world-rest-api
kubectl set image deployment hello-world-rest-api hello-world-rest-api=home/hello-world-rest-api:0.0.3.RELEASE --record=true
kubectl rollout undo deployment hello-world-rest-api --to-revision=1

kubectl logs hello-world-rest-api-58ff5dd898-6ctr2
kubectl logs -f hello-world-rest-api-58ff5dd898-6ctr2

kubectl get deployment hello-world-rest-api -o yaml
kubectl get deployment hello-world-rest-api -o yaml > deployment.yaml
kubectl get service hello-world-rest-api -o yaml > service.yaml
kubectl apply -f deployment.yaml
kubectl get all -o wide
kubectl delete all -l app=hello-world-rest-api

kubectl get svc --watch
kubectl diff -f deployment.yaml
kubectl delete deployment hello-world-rest-api
kubectl get all -o wide
kubectl delete replicaset.apps/hello-world-rest-api-797dd4b5dc

kubectl get pods --all-namespaces
kubectl get pods --all-namespaces -l app=hello-world-rest-api
kubectl get services --all-namespaces
kubectl get services --all-namespaces --sort-by=.spec.type
kubectl get services --all-namespaces --sort-by=.metadata.name
kubectl cluster-info
kubectl cluster-info dump
kubectl top node
kubectl top pod
kubectl get services
kubectl get svc
kubectl get ev
kubectl get rs
kubectl get ns
kubectl get nodes
kubectl get no
kubectl get pods
kubectl get po

kubectl delete all -l app=hello-world-rest-api
kubectl get all

kubectl apply -f deployment.yaml
kubectl apply -f ../currency-conversion/deployment.yaml

```
