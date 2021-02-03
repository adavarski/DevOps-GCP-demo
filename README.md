
Requirements:

- Terraform
- gcloud-sdk
- kubernetes-cli

Install Cloud SDK (gcloud, gsutil, bq, etc.)

Note: Cloud SDK requires Python; supported versions are Python 3 (preferred, 3.5 to 3.8) and Python 2 (2.7.9 or higher).

```
curl -O https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-sdk-326.0.0-linux-x86_64.tar.gz
tar -zxvf google-cloud-sdk-326.0.0-linux-x86_64.tar.gz 
```
Optional. Use the install script to add Cloud SDK tools to your path. You'll also be able to opt-in to command-completion for your shell and usage statistics collection. Run the script using this command:
```
./google-cloud-sdk/install.sh
```
Run gcloud init to initialize the SDK:
```
./google-cloud-sdk/bin/gcloud init
```
Check:
```
$ ./google-cloud-sdk/bin/gcloud config list
[core]
account = YOUR_GOOGLE_ACCOUNT@gmail.com
disable_usage_reporting = True
project = PROJECT_ID

Your active configuration is: [default]
```

Simpe demo:

1.Terraform GCP VM (example NGINX server) -> VM

2.Terraform GKE + manifests -> GKE

