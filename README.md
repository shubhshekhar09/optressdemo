# OPStressdemo


httpbin demo for OPSTree Solution

## Installation

Use the created helm to install httpbin or you can use manifest files to deploy the application.

```bash
helm install <package name>
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

