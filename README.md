# Infrastructure Automation Kubernetes Week 3

## Introduction

We will be using what weve learned in the previous weeks and deploy our own application. A PHP Guestbook Application with Redis.


## Objectives

Using what we have learned before, we are going to deploy an application on kubernetes.


What were going to deploy
- A single-instance Redis master to store guestbook entries
- Multiple replicated Redis instances to serve reads
- Multiple web frontend instances


---
## Getting Started:

1 - Copy the starter code from here into a new, private repository in your personal GitHub account. When adding a collaborator, be sure to add me ("cscc-luke-rouker").


2 - You need minikube up and running before going through the examples.

Start minikube using the command:
```
$ minikube start
```

If you do not have this setup please go to the [pre-lab] and follow those instructions before continuing.

Please make sure your minikube is cleaned, by deleting all contexts, resources, configs, pods, and namespaces made.

You can do it using the `kubectl delete <resource> <name>` command or go with the scorched earth method and run ...

```
$ minikube stop
$ minikube delete
$ minikube start
```

---

## Understanding the Starter Code
The application has been broken down into 6 parts
1. redis_deployment
2. redis_service
3. redis_deployment_2
4. redis_service_2
5. frontend_deployment
6. frontend_service

Within each directory, there is a readme with the excerise. Follow the directions, and update (if required) the provided manifest in each task directory under manifests. The general structure
of each yml is provided.


---

## Completing the Assignment


### 1 - Go through examples

Go through each of the directories provided, and complete the tasks.

The general manifest structures have been provided for ease of use, you are required to update it according to the task.


### 2 - Cleanup

```
kubectl delete deployment -l app=redis
kubectl delete service -l app=redis
kubectl delete deployment -l app=guestbook
kubectl delete service -l app=guestbook
```
  

---


## Submitting Your Work

1-  Publish your repository as a private repo, and ensure that you have pushed the latest version

2-  Submit the assignment in Blackboard with the link to your repo

[pre-lab]: https://github.com/cscc-afarag/kubernetes-week-1/blob/master/ENV_SETUP.md
