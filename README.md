# containerized-app-deployment-gke
Deploying a containerized application to Google Kubernetes Engine (GKE) using Docker and Kubernetes. Includes cluster setup, image build, deployment, and external access via Load Balancer
#  GKE Hello World Deployment

This project demonstrates deploying a containerized application to **Google Kubernetes Engine (GKE)** using Docker and Kubernetes.

---

##  Project Overview

- Create a GKE cluster
- Build a Docker image
- Push image to Google Container Registry
- Deploy application using Kubernetes
- Expose service via Load Balancer
- Access application publicly

---

##  Technologies Used

- Google Cloud Platform (GCP)
- Google Kubernetes Engine (GKE)
- Docker
- Kubernetes (kubectl)
- Container Registry

---

##  Steps

### 1. Set Compute Zone
```bash
gcloud config set compute/zone us-east1-d

2. Create Cluster

gcloud container clusters create hello-world

3. Build Docker Image

docker build -t gcr.io/$DEVSHELL_PROJECT_ID/hello-app:1.0 .

4. Push Image

gcloud docker -- push gcr.io/$DEVSHELL_PROJECT_ID/hello-app:1.0

5. Deploy Application

kubectl create deployment hello-app \
--image=gcr.io/$DEVSHELL_PROJECT_ID/hello-app:1.0

6. Expose Service

kubectl expose deployment hello-app \
--type=LoadBalancer \
--port=80 \
--target-port=8080

 Application Access

Retrieve external IP:

kubectl get svc hello-app

Then open:

http://EXTERNAL-IP

 Screenshots

Cluster Created

Docker Build

Push Image

Deployment

External IP

Application Running

 Result

Application successfully deployed and accessible via public IP showing:

Hello Kubernetes!

 Learning Outcome
 • Understanding Kubernetes architecture
 • Deploying containerized applications
 • Managing services and external access
 • Working with GKE and Docker integration

