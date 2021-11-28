# OPStressdemo


httpbin demo for OPSTree Solution

## Installation

Use the created helm to install httpbin or you can use manifest files to deploy the application.
```bash
NAMESPACE=ingress-basic

helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update

helm install ingress-nginx ingress-nginx/ingress-nginx --create-namespace --namespace $NAMESPACE 
```

```bash
helm install opstree-0.1.0.tgz
```
Output
```bash
shubhendu@Azure:~/optressdemo$ helm install --set "ingress.whitelistCIDR=1.1.1.2/1"opstree-demo test/opstree
NAME: opstree-demo
LAST DEPLOYED: Sun Nov 28 08:48:00 2021
NAMESPACE: default
STATUS: deployed
REVISION: 1
TEST SUITE: None
```

```bash

#for to install using kubectl
#change the directory to manifest folder
kubectl apply -f .
#or 
shubhendu@Azure:~$ kubectl apply -f https://raw.githubusercontent.com/shubhshekhar09/optressdemo/main/httpbin/manifest.yaml
#output be like
namespace/httpbin-demo created
serviceaccount/httpbin-demo created
service/httpbin-demo created
deployment.apps/httpbin-demo created
shubhendu@Azure:~$
```

## Usage

```bash
curl <load_balancer_ip>:port/<API_path>
```

