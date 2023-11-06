# Deploy Yolo Application to GKE(Google Kubernetes Engine) 
### Tech stack used:
- Node.js
- Docker
- Kubernetes
- Install [GCLI(Google Cloud CLI)](https://cloud.google.com/sdk/docs/install-sdk)
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
- [x] After setting up Google SDK CLI,create a kubernetes cluster on GKE.
    ```
    gcloud container clusters create week8-ip4 --num-nodes=3
    ```
- [x] Setup Connection to created GKE cluster in with your local machine or cloud shell.
    ```sh
    gcloud container clusters get-credentials week8-ip4 --zone us-central1-a --project <PROJECT_ID>
    ```
- [x] After cluster has been created,Apply manifest files to create deployment.
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

## Current setup is running on http://34.136.202.61/

### Cleanup
```sh
kubectl delete -f manifests
```

> Delete your GKE Cluster from GCP Console.