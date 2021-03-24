## Front End Service 

Finally, update the `manifests/guestbook-service.yml` so that it is a NodePort service that will expose the pods at port 80. 

Remember to use the correct selector to select the right `tier` and `app_name`

create and save this as  then apply it.

___
Once you have applied the manifest:
- verify using `kubectl get services`
- run `minikube service frontend --url`
- Copy and pasete the returned  url in your browser to view the guestbook
- Test the guestbook!
- Try scaling the deployment
  - `kubectl scale deployment frontend --replicas=5`
___