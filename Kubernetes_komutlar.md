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
___



## Pod oluşturma & değiştirme & silme komutları:

```
kubectl create -f [manifest_belge_adı]
```

```
kubectl apply -f [manifest_belge_adı]
```

```
kubectl run [pod_name] --image=nginx --restart=Never
```

```
kubectl run [pod_name] --generator=run-pod/v1 --image=nginx
```

```
kubectl run [pod_name] --image=nginx --restart=Never
```

```
kubectl delete pod [pod_name]
```

```
kubectl edit pod [pod_name] 
```
___

## Deployment/Namespace oluşturma & değiştirme & silme komutları:

```
kubectl create -f [name_of_file]
```

```
kubectl apply -f [name_of_file]
```

```
kubectl create deploy [deploy_name] --image=nginx
```

```
kubectl edit deploy [Deployment adı]
```

```
kubectl delete deploy [Deployment adı]
```

```
kubectl expose deploy [Deployment adı] --port=80 --type=NodePort
```

```
kubectl scale deploy [Deployment adı] --replicas=5
```

```
kubectl delete ns 
```

```
kubectl edit ns [Namespace adı]
```
___

## Servis değiştirme & silme komutları:

```
kubectl edit svc [Servis adı]
```

```
kubectl delete svc [Servis adı]
```
___

## Daemonset değiştirme & silme komutları:

```
kubectl edit ds [Daemonset adı] -n kube-system
```

```
kubectl delete ds [Daemonset adı]
```
___

## Service account değiştirme & silme komutları:

```
kubectl edit sa [sa_name]
```

```
kubectl delete sa [sa_name]
```
___

## Service oluşturma komutları:

```
kubectl create svc nodeport [Servis adı] --tcp=8080:80
```

## Pod arabirimine erişim komutu:

```
kubectl run [Pod adı] --image=busybox --rm -it --restart=Never -- sh
```
