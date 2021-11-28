# OPStressdemo


httpbin demo for OPSTree Solution

## Installation

Use the created helm to install httpbin or you can use manifest files to deploy the application.

```bash
helm install <package name>
#for to install using kubectl
#change the directory to manifest folder
kubectl apply -f .
```

## Usage

```bash
curl <load_balancer_ip>:port/<API_path>
```

