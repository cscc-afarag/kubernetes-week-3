## Redis Slaves

We will make our redis highly available by adding replica slaves. We will do this with another Deployment

##### We will be updating the manigest `manifests/redis-slave-deployment.yml` with the following:

1. name = redis-slave
2. metadata labels -> app_name = redis
3. For the selector match labels in the deployment-spec:
   1. app_name = redis
   2. role = slave
   3. tier = backend
4. 2 replicas
5. Our pod template should have the following labels:
   1. app_name = redis
   2. role = slave
   3. tier = backend
6. The container should have:
   1. name = slave
   2. image = `gcr.io/google_samples/gb-redisslave:v3`
   3. resource requests just like the master:
      1. cpu = 100m
      2. memory = 100Mi
   4. we need an env variable of name GET_HOSTS_FROM and value 'env'
   5. container port should be 6379

---
Once your manifest is ready:
-  use `kubectl apply` with the created manifest.
-  use `kubectl get pods` to verify
---
