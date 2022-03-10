___
# ⎈⎈⎈⎈⎈ KUBERNETES'de SIKLIKLA KULLANILAN KOMUTLAR ⎈⎈⎈⎈⎈


## Nodelar ile alakalı komutlar:

```
kubectl get no
```

```
kubectl get no -o wide
```

```
kubectl describe no
```

```
kubectl get no -o yaml
```

```
kubectl get node --selector=[label_name]
```
___


## Pod'lar ile alakalı komutlar:

```
kubectl get po
```

```
kubectl get po -o wide
```

```
kubectl describe po
```

```
kubectl get po --show-labels
```

```
kubectl get po -l app=techakademi/merhabadunya
```

```
kubectl get po -o yaml
```

```
kubectl get pod [pod_name] -o yaml --export
```

```
kubectl get pod [pod_name] -o yaml --export > belgeismi.yaml
```

```
kubectl get pods --field-selector status.phase=Running
```
___

## Namespace'lar ile alakalı komutlar:

```
kubectl get ns
```

```
kubectl get ns -o yaml
```

```
kubectl describe ns
```
___

## Deployment'lar ile alakalı komutlar:

```
kubectl get deploy
```

```
kubectl describe deploy
```

```
kubectl get deploy -o wide
```

```
kubectl get deploy -o yaml
```
___


## Servis'ler ile alakalı komutlar:

```
kubectl get svc
```

```
kubectl describe svc
```

```
kubectl get svc -o wide
```

```
kubectl get svc -o yaml
```

```
kubectl get svc --show-labels
```
___


## Daemonset'ler ile alakalı komutlar:

```
kubectl get ds
```

```
kubectl get ds --all-namespaces
```

```
kubectl describe ds [daemonset_name] -n [namespace_name]
```

```
kubectl get ds [ds_name] -n [ns_name] -o yaml
```
___

## Event'ler ile alakalı komutlar:

```
kubectl get events
```

```
kubectl get events -n kube-system
```

```
kubectl get events -w
```
___


## Log'lar ile alakalı komutlar:

```
kubectl logs [pod_name]
```

```
kubectl logs --since=1h [pod_name]
```

```
kubectl logs --tail=20 [pod_name]
```

```
kubectl logs -f -c [container_name] [pod_name]
```

```
kubectl logs [pod_name] > pod.log
```
___

## Replicaset'ler ile alakalı komutlar:

```
kubectl get rs
```

```
kubectl describe rs
```

```
kubectl get rs -o wide
```

```
kubectl get rs -o yaml
```
___

## Rol'ler ile alakalı komutlar:

```
kubectl get roles --all-namespaces
```

```
kubectl get roles --all-namespaces -o yaml
```
___


## Secret'lar ile alakalı komutlar:

```
kubectl get secrets
```

```
kubectl get secrets --all-namespaces
```

```
kubectl get secrets -o yaml
```
___

## Configmap'lar ile alakalı komutlar:

```
kubectl get cm
```

```
kubectl get cm --all-namespaces
```

```
kubectl get cm --all-namespaces -o yaml
```
___

## Ingress ile alakalı komutlar:

```
kubectl get ing
```

```
kubectl get ing --all-namespaces
```
___


## Persistent Volume ile alakalı komutlar:

```
kubectl get pv
```

```
kubectl describe pv
```

```
kubectl get pvc 
```

```
kubectl describe pvc
```

## StorageClass ile alakalı komutlar:

```
kubectl get sc
```

```
kubectl get sc -o yaml
```
___

## Birden fazla kaynağı görütüleme komutları:

```
kubectl get svc, po
```

```
kubectl get deploy, no
```

```
kubectl get all
```

```
kubectl get all --all-namespaces
```
___


## Etiketleme (Label) komutları:

```
kubectl label [node_name] disktype=ssd
```

```
kubrectl label [pod_name] env=prod
```
|||

# nodes/pods
kubectl delete node [node_name]
kubectl delete pod [pod_name]
kubectl edit node [node_name]
kubectl edit pod [pod_name] 

# deployments/namespaces
kubectl edit deploy [deploy_name]
kubectl delete deploy [deploy_name]
kubectl expose deploy [deploy_name] --port=80 --type=NodePort
kubectl scale deploy [deploy_name] --replicas=5
kubectl delete ns 
kubectl edit ns [ns_name]

# services
kubectl edit svc [svc_name]
kubectl delete svc [svc_name]

# daemonsets
kubectl edit ds [ds_name] -n kube-system
kubectl delete ds [ds_name]

# serviceaccounts
kubectl edit sa [sa_name]
kubectl delete sa [sa_name]

# annotate
kubectl annotate po [pod_name] [annotation]
kubectl annotate no [node_name]

########### ADDING RESOURCES ###############
# creating a pod
kubectl create -f [name_of_file]
kubectl apply -f [name_of_file]
kubectl run [pod_name] --image=nginx --restart=Never
kubectl run [pod_name] --generator=run-pod/v1 --image=nginx
kubectl run [pod_name] --image=nginx --restart=Never

# creating a service
kubectl create svc nodeport [svc_name] --tcp=8080:80

# creating a deployment
kubectl create -f [name_of_file]
kubectl apply -f [name_of_file]
kubectl create deploy [deploy_name] --image=nginx

# interactive pod
kubectl run [pod_name] --image=busybox --rm -it --restart=Never -- sh

# output YAML to a file
kubectl create deploy [deploy_name] --image=nginx --dry-run -o yaml > deploy.yaml
kubectl get po [pod_name] -o yaml --export > pod.yaml

# getting help
kubectl -h 
kubectl create -h
kubectl run -h
kubectl explain deploy.spec

# API calls
kubectl get --raw /apis/metrics.k8s.io/

# cluster info
kubectl config 
kubectl cluster-info
kubectl get componentstatuses
