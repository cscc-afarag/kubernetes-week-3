
## Redis Master Service

For the guestbook application to communicate with redis we need to create a service to proxy traffic to the redis master pod.

##### We will be updating the manigest `manifests/redis-master-service.yml` with the following:

1. name = redis-master
2. metadata labels
   1. app_name = redis
   2. role = master
   3. tier = backend
3. the spec should map port 6379 to the port 6379 on the pod
4. Selector
   1. *What should we use as the* `selector`?


---
Once your manifest is ready:
-  use `kubectl apply` with the created manifest.
-  use `kubectl get service` to verify its running
---