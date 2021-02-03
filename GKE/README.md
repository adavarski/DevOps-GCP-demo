Sign up/in for GCP.
Create a new Google Cloud Project (Demo)
Create service account for terraform (Name: demo-terraform; Role: Owner or Kubernetes Engine Admin/Storage Admin/Service Account User), servcie account key (ADD KEY: Select JSON as the key type and click Create) and downloaded JSON credentials
Copy credentials.json file to the project directory for this demo.
Enable Compute Engine API &  Kubernetes Engine API (APIs & Services) 
All instances in this project inherit these SSH keys ---> ssh-keygen and add ssh pub key (Compute Engine/Metadata/SSH Keys -> add davar:generated pub key)
Run vim main.tf to set the project ID.
```
terraform init.
terraform fmt/plan.
terraform apply.
```
```
gcloud components install kubectl
gcloud config set project PROJECT_ID set the current project,
gcloud container clusters list (to list clusters),
gcloud container clusters get-credentials gke-demo to setup kubeconfig,
#Now you can access your cluster using the Kubernetes CLI: kubectl cluster-info.
```
