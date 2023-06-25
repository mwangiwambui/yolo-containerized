# Requirements
Make sure you have a google project with the following services enabled
- Artifact Registry
- Cloud Build
- Google Kubernetes Engine APIs
## To create the image repositories on GCP
The client repository
 ```
 gcloud artifacts repositories create yolo-client \
    --project=grand-highway-256907 \
    --repository-format=docker \
    --location=us-central1 \
    --description="Docker repository" 
  ```
The backend repository
 ```
 gcloud artifacts repositories create yolo-backend \
    --project=grand-highway-256907 \
    --repository-format=docker \
    --location=us-central1 \
    --description="Docker repository for backend"

  ```

## To build the image from the docker files within the specific folders 
Backend image
` cd backend `
 ```
  gcloud builds submit \
  --tag us-central1-docker.pkg.dev/grand-highway-256907/yolo-backend/yolo-gke .
 ```

Frontend Image
` cd client `
```
  gcloud builds submit \
  --tag us-central1-docker.pkg.dev/grand-highway-256907/yolo-client/yolo-gke .
 ```

## Run the following to deploy after setting up your clusters
 `kubectl apply -f client-deployment.yaml`

 For the backend deployment
 `kubectl apply -f client-deployment.yaml`
## Run the following to set up the service
 `kubectl apply -f backend-service.yaml`

 For the client service
 `kubectl apply -f backend-service.yaml`

 ## Link to my service
 http://34.170.19.106:3000/

 
