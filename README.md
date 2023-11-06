# Deploy Yolo Application to GKE(Google Kubernetes Engine) 
### Tech stack used:
- Node.js
- Docker
- Kubernetes
- GKE(Google Kubernetes Engine)


# Steps

- [x] Create a folder named `manifests`  and kubernetes deployments files there:

    ```
      backend-deployment.yml
      client-deployment.yml
      persistent-volume-claim.yml
      mongo-deployment.yml
      mongo-config.yml
    ```
- [x] Create a kubernetes cluster on GKE.
- [x] Setup Connection to created GKE cluster in with your local machine or cloud shell.
    ```sh
    gcloud container clusters get-credentials <CLUSTER_NAME> --zone <ZONE> --project <PROJECT_ID>
    ```
- [x] Apply manifest files to create deployment.
    ```sh
    kubectl apply -f manifests
    ```
- [x] Check status of all deployments.
    ```sh
    kubectl get all
    ```
- [x] Check status of service.
    ```sh
    kubectl get svc
    ```
- [x] Check the external IP of the service in the browser.

### Cleanup
```sh
kubectl delete -f manifests
```

> Delete your GKE Cluster from GCP Console.