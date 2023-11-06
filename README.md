# Deploy Yolo Application to GKE(Google Kubernetes Engine) 
### Tech stack used:
- Node.js
- Docker
- Kubernetes
- GKE(Google Kubernetes Engine)


# Steps
- [x] Clone the repository
    ```
    git clone https://github.com/SimonOkello/yolo.git
    ```

- [x] Checkout to `week8-ip4` branch
    ```
    git checkout week8-ip4
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