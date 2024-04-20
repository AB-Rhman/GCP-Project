# GCP Project with Flask and Kubernetes
This repository contains a simple example application built with Flask and deployed using Docker on Google Kubernetes Engine (GKE) in Google Cloud Platform (GCP). The deployment process is automated using Cloud Build and Cloud Build Triggers.

## Overview

The project demonstrates the deployment of a Flask application using Docker containers on a GKE cluster. Cloud Build and Cloud Build Triggers are utilized to automate the build and deployment process.

## Prerequisites

Before getting started, ensure you have the following prerequisites:

- A Google Cloud Platform (GCP) account
- Google Cloud SDK installed on your local machine
- Basic understanding of Docker, Kubernetes, and Git

##  Getting Started
To replicate this project and automate the deployment process to GKE, follow these steps:

### 1. Clone the Repository
Clone this repository to your local machine:
```bash
git clone https://github.com/AB-Rhman/GCP-Project.git
```

### 2. Set Up GCP Account and Project
- If you haven't already, sign up for a Google Cloud Platform account.
- Create a new GCP project or use an existing one.

### 3. Install Google Cloud SDK
Install the Google Cloud SDK on your local machine following the instructions [here](https://cloud.google.com/sdk/docs/install).

### 4. Configure Google Cloud SDK
Run the following command and follow the prompts to authenticate and set up your Google Cloud SDK:
```bash
gcloud init
```

### 5. Set Up GKE Cluster
Create a GKE cluster in your GCP project using the following command:
```bash
gcloud container clusters create [CLUSTER_NAME] --num-nodes=3 --zone=[COMPUTE_ZONE]
```
Replace [CLUSTER_NAME] with your desired cluster name and [COMPUTE_ZONE] with your preferred compute zone.

> Make sure kubectl is configured to use this cluster.

**Alternatively**, you can use the GUI on the GCP Platform, which may be more intuitive : )

### 6. Create Cloud Build Trigger
In the GCP Console, navigate to Cloud Build > Triggers and create a new trigger. Link it to your GitHub repository and use the provided cloudbuild.yaml file for build configuration.

### 7. Push Changes to Main Branch
Make any desired changes to your application code, commit them, and push to the main branch of your GitHub repository:
```bash
git add .
git commit -m "Your commit message here"
git push origin main
```

### 8. Automated Deployment
Once changes are pushed to the main branch, Cloud Build Trigger will automatically build a Docker image, push it to Container Registry, and deploy it to your GKE cluster.


### Additional Notes
- *Ensure that necessary permissions are granted to Cloud Build for accessing your GCP resources.*
- *Customize the cloudbuild.yaml file as per your project requirements.*
- *Monitor Cloud Build logs for any build or deployment errors.*
