# kubernetes

Commands used for ReplicationController
-----------------------------------------
1. kubectl get pods
2. kubectl get pods -o wide
3. kubectl get pods -l app=nginx
4. kubectl get rc
5. kubectl get rc nginx
6. kubectl describe rc nginx
7. kubectl scale rc nginx --replicas=4
8. kubectl create -f replicationController.yaml
9. kubectl delete -f replicationController.yaml

Commands used for ReplicaSet
----------------------------
1. kubectl create -f replicaSet.yaml
2. kubectl get pods
3. kubectl get pods -l tier=frontend
4. kubectl get rs nginx-rs
5. kubectl get rs nginx-rs -o wide
6. kubectl describe rs nginx-rs
7. kubectl get po -o wide
8. kubectl scale rs nginx-rs --replicas=5
9. kubectl delete -f replicaSet.yaml


ReplicaSet(Newer Version) and ReplicationController(Older Version) both are same. Only difference is that RC supports Equality-based Selectors whereas RS supports Set-based Selectors.

<br/><img width="750" height="250" src="https://user-images.githubusercontent.com/19406666/159111099-b74a46a1-8de7-453d-a2b3-bd3e43687769.png">

<br/><img width="750" height="250" src="https://user-images.githubusercontent.com/19406666/159111162-a2ae69ec-2ce9-4ee4-9c79-c0f62408f509.png">



Commands used for Deployment
----------------------------
1. kubectl create -f deployment.yaml
2. kubectl get pods
3. kubectl describe deployment nginx-deploy
4. kubectl get po -l app=nginx-app
5. kubectl get rs -l app=nginx-app
6. kubectl get deploy -l app=nginx-app
7. RollingUpdate: kubectl set image deploy nginx-deploy nginx-container=nginx:1.9.1  OR kubectl edit deploy nginx-deploy
8. kubectl rollout status deployment/nginx-deploy
9. kubectl get deploy
</br>**Rollback Deployment:**
11. kubectl set image deploy nginx-deploy nginx-container=nginx:1.91 --record
12. kubectl rollout status deployment/nginx-deploy
13. kubectl rollout history deployment/nginx-deploy
14. kubectl rollout undo deployment/nginx-deploy
15. kubectl scale deployment nginx-deploy --replicas=2

Deployment uses replicaSet behind the scenes.


Services in Kubernetes
----------------------------
When webapp is deployed:
1. How does this front end webapp is exposed to the outside world?
2. How do frontend webapp is connected to backend database?
3. How do we resolve Pod IP Changes, when they die?

Why do we need Services:
1. Is it possible to have permanent IP Address?
2. How do various components connect & communicate?
3. How do applications are exposed to outside world?

Types of Services:
<br/><img width="750" height="250" alt="image" src="https://user-images.githubusercontent.com/19406666/161389127-74269447-e852-4835-bea3-03cfdceaa7a8.png">

**NodePort**:
<br/><img width="550" height="250" alt="image" src="https://user-images.githubusercontent.com/19406666/161582426-a91ae33a-0805-49d9-98a7-422d5135cd57.png">
<br/><img width="750" height="250" alt="image" src="https://user-images.githubusercontent.com/19406666/161582739-485f8932-594d-491b-90f0-c9e4fa141b05.png">
<br/><img width="750" height="250" alt="image" src="https://user-images.githubusercontent.com/19406666/161582810-9ac0da3a-0f49-48f5-9da9-481143ce8da3.png">
<img width="750" height="250" alt="image" src="https://user-images.githubusercontent.com/19406666/169760416-1984002c-d8a2-42b8-9d0f-b33ae77c3dfb.png">


