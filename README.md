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
helm repo add optress https://shubhshekhar09.github.io/optressdemo/
helm repo list
#so i want to whitelist ip CIDR 1.1.1.2/1
helm install --set "ingress.whitelistCIDR=1.1.1.2/1" optress optress/opstree
NAME: optress
LAST DEPLOYED: Sun Nov 28 10:16:07 2021
NAMESPACE: default
STATUS: deployed
REVISION: 1
TEST SUITE: None

shubhendu@Azure:~/optressdemo$ kubectl get ingress -A
NAMESPACE   NAME           CLASS    HOSTS   ADDRESS        PORTS   AGE
default     httpbin-demo   <none>   *       52.150.48.33   80      78s

shubhendu@Azure:~/optressdemo$ curl -o /dev/null -s -w "%{http_code}\n" 52.150.48.33
#output
200
shubhendu@Azure:~/optressdemo$
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
Accessing from certain ip

```bash
shubhendu@Azure:~/optressdemo$ curl -o /dev/null -s -w "%{http_code}\n" 52.150.48.33
403
shubhendu@Azure:~/optressdemo$
```

As you see getting 403

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
