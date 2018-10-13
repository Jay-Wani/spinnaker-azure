# spinnaker-azure
spinnaker on azure kubernetes service (AKS)



# Continuous Deployment to Kubernetes

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2F301-jenkins-acr-spinnaker-k8s%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>
<a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2F301-jenkins-acr-spinnaker-k8s%2Fazuredeploy.json" target="_blank">
    <img src="http://armviz.io/visualizebutton.png"/>
</a>

## A. Deploy

Create service principle

```bash
az login
az account set --subscription <Subscription ID>
az ad sp create-for-rbac --name "Spinnaker"
```
   
```bash
ssh -i <path to private key file> -L 8080:localhost:8080 -L 9000:localhost:9000 -L 8084:localhost:8084 -L 8001:localhost:8001 <User name>@<Public DNS name of instance you just created>
```

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```


## Connect to Spinnaker

Navigate to http://localhost:9000/ on your local machine.
Navigate to 'Applications -> {Application Name} -> Pipelines' to see your pipeline. Follow steps [here](http://www.spinnaker.io/docs/kubernetes-source-to-prod#section-1-create-a-spinnaker-application) to create a pipeline manually.


