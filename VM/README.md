### Terraform GCP VM: example NGINX server

This folder contains a simple Terraform module that deploys resources in GCP for a web server

Running this module manually

Prequisites: locally installed terraform

- Sign up/in for GCP.
- Create a new Google Cloud Project (Demo)
- Create service account for terraform (Name: demo-terraform; Role: Owner or Role for Compute Engine), service account key (ADD KEY: Select JSON as the key type) and downloaded JSON credentials
- Copy credentials.json file to the project directory for this demo.
- Enable Compute Engine API (APIs & Services) 
- Add SSH key: ssh-keygen and add ssh pub key (Compute Engine/Metadata/SSH Keys -> add davar:generated google_compute_engine.pub key). Note: All instances in this project inherit these SSH keys 
- Run vim main.tf to set the project ID.
- Terraforming: terraform init/plan/apply and check nginx

Example Output:
```
terraform init.
terraform fmt/plan.
terraform apply.

Apply complete! Resources: 3 added, 0 changed, 0 destroyed.

Outputs:

ip = "104.197.88.27"

#Check nginx
http://104.197.88.27/ ---> Welcome to nginx!

#Login to VM
$ ssh -i ~/.ssh/google_compute_engine ubuntu@35.223.180.23 (or ssh -i ~/.ssh/google_compute_engine davar@35.223.180.23)
The authenticity of host '35.223.180.23 (35.223.180.23)' can't be established.
ECDSA key fingerprint is SHA256:4bkLYjdxXUcnR6VAY5riK8vgW/MmAX7hC30ERgIjgHI.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added '35.223.180.23' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 5.4.0-1036-gcp x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Wed Feb  3 10:29:09 UTC 2021

  System load:  0.98              Processes:           102
  Usage of /:   17.2% of 9.52GB   Users logged in:     0
  Memory usage: 40%               IP address for ens4: 10.128.0.4
  Swap usage:   0%

4 packages can be updated.
4 of these updates are security updates.
To see these additional updates run: apt list --upgradable

```

- When you're done, run `terraform destroy` to clean resources.

