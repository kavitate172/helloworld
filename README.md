helloworld/ ├── .github/
                       │ └── workflows/ │ 
                                        └── deploy.yml # GitHub Actions CI/CD workflow 
            ├── k8s/ │ 
                     ├── deployment.yaml # Kubernetes Deployment manifest │ 
                     └── service.yaml # Kubernetes Service manifest 
            ├── app.js # Node.js application code 
            ├── package.json # Node.js dependencies and scripts 
            ├── Dockerfile # Docker container configuration 
            ├── .gitignore # Files to ignore in version control 
            └── README.md # This documentation file


Run
Copy code

## 🚀 Getting Started

### Prerequisites
- GitHub account
- k3s Kubernetes cluster
- kubectl configured with cluster access

### Installation

Set up GitHub Secrets:
K3S_KUBECONFIG: Base64-encoded kubeconfig (cat ~/.kube/config | base64 -w0)
(Optional) Configure additional secrets as needed
🛠️ Configuration Files
1. Node.js Application (app.js)
Simple HTTP server that responds with "Hello World":

2. Dockerfile
Container configuration for the Node.js app:

3. Kubernetes Manifests (k8s/)
deployment.yaml: Defines the app deployment with 2 replicas
service.yaml: Creates a ClusterIP service exposing port 80
4. GitHub Actions Workflow (.github/workflows/deploy.yml)
Automates:

Building and pushing Docker image to GHCR
Deploying to k3s cluster
Using kubectl for deployment management
🔄 CI/CD Pipeline
The workflow triggers on:

Pushes to the main branch
Manual triggers via GitHub UI
Steps:

Checkout code
Login to GitHub Container Registry
Build and push Docker image
Install kubectl
Deploy to k3s cluster
