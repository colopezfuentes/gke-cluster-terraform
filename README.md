# GKE Cluster terraform

## Deploying infrastructure

### Authenticate with service account
In this part is important to create a ```service account``` for connecting to GCP Console and can provision the infrastructure

### Setting variables

```
export GOOGLE_APPLICATION_CREDENTIALS={SERVICE_ACCOUNT_JSON}
export GOOGLE_PROJECT={MY_PROJECT}
export GOOGLE_REGION={MY_REGION}
```
### Initialize the project

```
terraform init \
-backend-config="bucket=$BUCKET_NAME" \ 
-backend-config="prefix=$PREFIX"
```

### Generate plan

``` 
terraform plan
```

### Apply changes
```
terraform apply
```

### Destroy infrastucture

```
terraform destroy
```

## Connecting to private GKE Cluster

### Connect to the Bastion host

```
gcloud compute ssh {BASTION_HOST_NAME} --zone {REGION_NAME}
```

### Authenticate to the GCP console
```
gcloud auth login {ACCOUNT}
```

### Authenticate to GKE Cluster 

```
gcloud container clusters get-credentials {CLUSTER_NAME} --region {REGION_NAME} --project {PROJECT_NAME}
```
## Create Deployment and Services

Review these example instructions -> https://github.com/colopezfuentes/workloads-kubernetes


