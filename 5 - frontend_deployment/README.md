
## Front End Deployment

The guestbook application has a web frontend. It is preconfigured to connect to the redis-master service for writes and redis-slave for reads.

update the `manifests/guestbook-deployment.yml` so it looks like the following

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: frontend
  labels:
    app_name: guestbook
spec:
  selector:
    matchLabels:
      app_name: guestbook
      tier: frontend
  replicas: 3
  template:
    metadata:
      labels:
        app_name: guestbook
        tier: frontend
    spec:
      containers:
      - name: php-redis
        image: gcr.io/google-samples/gb-frontend:v4
        resources:
          requests:
            cpu: 100m
            memory: 100Mi
        env:
        - name: GET_HOSTS_FROM
          value: env
        ports:
        - containerPort: 80
```

---
Once your manifest is ready:
-  use `kubectl apply` with the created manifest.
-  use `kubectl get pods` to verify its running
---
