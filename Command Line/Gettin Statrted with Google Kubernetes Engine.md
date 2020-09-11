# LAB: Google Cloud Fundamentals, Getting Started with Google Kubernetes Engine.

# Objectives

In this Lab we Learn how to perfrom the following operations

-Provision a Kubernetes Cluster using Kubernetes Engine

-Deploy and manage Docker containers using Kubectl

## Steps

1. Start a Kubernetes Engine Cluster.

  -Activate the cloud shell, for convenience assign the zone you want to work with in an environment Variable
    export MY_ZONE=us-central1-a

  -Start a Kubernetes cluster managed by Kubernetes Engine.(This command automatically authenticates kubectl)
    gcloud container clusters create webfrontend --zon $MY_ZONE --num-nodes 2

  -check your installed version of kubernetes.
    kubectl version

  -View your running nodes in the GCP Console.
    gcloud compute instances list

2. Run and Deploy a Container
    -Launch a single instance of the nginx container.
      kubectl create deploy nginx --image=ngiinx:1.17.10
    
    -View the pod running the nginx container
      kubectl get pods

    -Expose the nginx container to the internet.
      kubectl expose deployment nginx --port 80 --type LoadBalancer

    -View the new service
      Kubectl get services

    -Open your Clusters external Ip Address in a new Browser Tab

    -Scale up the number of pods running on your service
      kubectl scale deployment nginx --replicas 3

    -Confirm that kubernetes has updated the number of pods.
      kubectl get pods

    -Confirm your External Ip address has not changed
       Kubectl get services

    -Return to the browser you viewed your clusters external IP. Refresh to confirm that the nginx web server is still responding
  