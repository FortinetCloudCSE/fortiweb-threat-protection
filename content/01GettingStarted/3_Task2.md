---
title: "Task 2 - Run Terraform"
weight: 3
---

### Task 2 - Launch resources using Terraform

All the components required for Lab1 and Lab2 are deployed through terraform. 

Here is the Architecture diagram for Lab1: 

![lab1diagram](../images/.jpg)

Perform the following steps in your Cloudshell console to create your environment.

1. Clone the Github repo `git clone https://github.com/FortinetCloudCSE/fortiweb-threat-protection.git`
2. Change directory to the `cd FortiWeb-threat-protection/terraform` folder
3. Run `terraform init`

```sh
git clone https://github.com/FortinetCloudCSE/fortiweb-threat-protection.git
cd FortiWeb-threat-protection/terraform
terraform init
```

![lab11](../images/terraform1.jpg)



4. Run `terraform apply  -var='username=UserXX' --auto-approve`

    Your username can be found in the login email.  
    Say your Azure account login is fweb11@ftntxxxxx.onmicrosoft.com, your username is **fweb11** 

```sh
terraform apply  -var='username=UserXX' --auto-approve
```

![lab12](../images/terraform2.jpg)
    
6. Terraform deployment takes atleast 25-30 min to complete. Please copy the output once the deployment is succeeded. 

![lab13](../images/terraformoutput.jpg)