#### Terraform GKE + simple demo 

- Sign up/in for GCP
- Create a new Google Cloud Project (Demo)
- Create service account for terraform (Name: demo-terraform; Role: Owner or Roles: Kubernetes Engine Admin/Storage Admin/Service Account User), service account key (ADD KEY: Select JSON as the key type) and download JSON credentials
- Copy downloaded JSON credentials file as credentials.json file to the project directory for this demo.
- Enable Kubernetes Engine API & Compute Engine API (APIs & Services) 
- Add SSH keys: ssh-keygen and add ssh pub key (Compute Engine/Metadata/SSH Keys -> add davar:generated pub key). Note: All instances in this project inherit these SSH keys 

- Run vim main.tf to set the project ID, etc.
- Terraforming: terraform init/plan/apply
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
- Clean: `terraform destroy`
