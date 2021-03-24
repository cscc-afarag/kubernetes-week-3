
## Redis Master
*redis is used by the guestbook application to store its data*

The application will write to a master and read from multiple slave instances.

## Redis Deployment

##### We will be updating the `manifest/redis-master-deployment.yml`

Update the manifest with the following values:
  
1. Metadata: name = redis-master and labels app = redis
2. For the deployment spec use a selector and matchLabels 
   1. app_name = redis
   2. role = master
   3. tier = backend
3. 1 replica
4. for the pod template add the following labels:
   1. app_name = redis
   2. role = master
   3. tier = backend
5. The container for the pod template should have:
   1. name = master
   2. use the image  `k8s.gcr.io/redis:e2e`
   3. Have a resource request:
      1. cpu 100m
      2. memort 100Mi
   4. container port = 6379

---
Once your manifest is ready:
-  use `kubectl apply` with the created manifest.
-  verify your pod is up with `kubectl get pods`
-  get the logs via `kubectl logs -f <pod-name>`
---
