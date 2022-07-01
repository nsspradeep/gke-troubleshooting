# Lab Setup

## Test Cluster 1

Create GKE cluster using below gcloud command:

```shell 
 gcloud beta container clusters create test-cluster-1 \
 --zone=us-central1-a \
 --num-nodes=3 \
 --machine-type=n1-standard-1 \
 --disk-size=100 \
 --disk-type=pd-standard \
 --image-type=COS \
 --enable-autorepair \
 --enable-autoupgrade \
 --enable-autoscaling \
 --max-nodes=3 \
 --min-nodes=0 
```
 
 ### Test 1
 Deploy testapp-1 on test-cluster-1 
 ```
 kubectl create -f testapp-1.yaml
 ```
 
 ### Test 2
 Deploy testapp-2 on test-cluster-1
 ```
 kubectl create -f testapp-2.yaml
 ``` 
 
 ### Test 3
 Deploy testapp-3 on test-cluster-1
 ```
 kubectl create -f testapp-3.yaml
 ``` 
 ## Test Cluster 2
 
 Create GKE cluster using below gcloud command:
 
```shell
gcloud beta container clusters create test-cluster-2 \
 --zone=us-west2-a \
 --num-nodes=3 \
 --machine-type=n1-standard-4 \
 --disk-size=100 \
 --disk-type=pd-standard \
 --image-type=COS \
 --enable-autorepair \
 --enable-autoupgrade \
 --enable-autoscaling \
 --max-nodes=50 \
 --min-nodes=0
 ```
 
 ### Test 4
 Deploy testapp-4 on test-cluster-2
 ```
 kubectl create -f testapp-4.yaml
 ```

## Test Cluster 3

Create GKE cluster using below gcloud command:

```shell
gcloud compute networks create cluster-10-network --subnet-mode=custom
gcloud beta container clusters create test-cluster-3 \
 --network=cluster-10-network \
 --create-subnetwork name=cluster-10-subnet \
 --cluster-version=1.22.8-gke.202 \
 --master-ipv4-cidr= \
 --cluster-ipv4-cidr=10.0.2.0/24 \
 --services-ipv4-cidr=10.0.3.0/24 \
 --zone=us-central1-c \
 --release-channel=regular \
 --default-max-pods-per-node=110 \
 --enable-ip-alias \
 --enable-stackdriver-kubernetes \
 --enable-shielded-nodes \
 --addons=HttpLoadBalancing,HorizontalPodAutoscaling,GcePersistentDiskCsiDriver \
 --node-version=1.22.8-gke.202 \
 --num-nodes=1 \
 --machine-type=e2-medium \
 --disk-size=100 \
 --disk-type=pd-standard \
 --node-locations=us-central1-c \
 --max-surge-upgrade=1 \
 --max-unavailable-upgrade=0 \
 --image-type=COS_CONTAINERD \
 --max-pods-per-node=110 \
 --enable-autorepair \
 --enable-autoupgrade \
 --enable-autoscaling \
 --max-nodes=30 \
 --min-nodes=0 \
 --no-shielded-secure-boot \
 --scopes=https://www.googleapis.com/auth/devstorage.read_only,https://www.googleapis.com/auth/logging.write,https://www.googleapis.com/auth/monitoring,https://www.googleapis.com/auth/servicecontrol,https://www.googleapis.com/auth/service.management.readonly,https://www.googleapis.com/auth/trace.append
```

### Test 5
 Deploy testapp-5 on test-cluster-3
 ```
 kubectl create -f testapp-5.yaml
 ```
