## Redis Slave Service

Now that we have made the slaves, lets also expose them with a service.

##### We will be updating the manigest `manifests/redis-slave-service.yml`:

*Using what we know and what we did in the master service manifest, create your service and apply it*

---
Once your manifest is ready:
-  use `kubectl apply` with the created manifest.
-  use `kubectl get service` to verify its running
---
