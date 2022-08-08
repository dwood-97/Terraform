This lab uses Kubernetes and Terraform while Exploring Terraform State Functionality

To see what the state file is doing we can start with a:
terraform state list

Then to see what the state file is tracking we can use:
terraform state show "paste the file shwon from previous command" | egrep "what you want to track"

In this case we will track "replicas" from the deployment file like this:

##INPUT##

[cloud_user@ip-10-0-1-98 section2-hol1]$ terraform state list

##OUTPUT##

kubernetes_deployment.tf-k8s-deployment
kubernetes_service.tf-k8s-service

##INPUT##

[cloud_user@ip-10-0-1-98 section2-hol1]$ terraform state show kubernetes_deployment.tf-k8s-deployment | egrep replicas

##OUTPUT##

        replicas                  = "2"