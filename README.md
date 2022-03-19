# kubernetes

1. kubectl get pods
2. kubectl get pods -o wide
3. kubectl get pods -l app=nginx
4. kubectl get rc
5. kubectl get rc nginx
6. kubectl describe rc nginx
7. kubectl scale rc nginx --replicas=4
8. kubectl create -f replicationController.yaml
9. kubectl delete -f replicationController.yaml

ReplicaSet(Newer Version) and ReplicationController(Older Version) both are same. Only difference is that RC supports Equality-based Selectors whereas RS supports Set-based Selectors.

<img width="1477" alt="image" src="https://user-images.githubusercontent.com/19406666/159111099-b74a46a1-8de7-453d-a2b3-bd3e43687769.png">
