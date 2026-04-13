# K-Commerce Helm Demo

This project is a hands-on learning lab created to master the fundamentals of **Helm Charts** and **Kubernetes** orchestration. It demonstrates how to package, deploy, and manage simple microservices within a local cluster environment.

##  Project Objectives
- Transition from manual Kubernetes manifests to a structured **Helm** deployment.
- Understand the core directory structure: `Chart.yaml`, `values.yaml`, and `templates/`.

##  Project Structure
```text
k-commerce/
├── payments/        # Helm chart for the Payment Microservice
├── shipping/        # Helm chart for the Shipping Microservice
├── screenshots/     # Visuals of deployment and logs
└── README.md        # Project documentation


Getting Started
1. Prerequisites
Minikube installed and running.

Helm 3 installed and configured in your environment.

2. Installation
Navigate to the root k-commerce directory in your terminal and run:

PowerShell
# Install the Payments Microservice
helm install payments-release ./payments

# Install the Shipping Microservice
helm install shipping-release ./shipping
3. Verification
Verify that the pods are running and check the service logs to see the printed messages:

PowerShell
# List all running pods to verify status
kubectl get pods

# View logs for the Payments service
kubectl logs -l app.kubernetes.io/instance=payments-release

# View logs for the Shipping service
kubectl logs -l app.kubernetes.io/instance=shipping-release
  Lessons Learned & Troubleshooting
This project involved solving several real-world DevOps scenarios:

Template Debugging: Fixed nil pointer evaluating interface errors by ensuring values.yaml properly defined all keys used in the templates.

Chart Optimization: Cleaned up the default helm create boilerplate by removing unused files (like tests/ and NOTES.txt) to maintain a lightweight deployment.

  Proof of Work
The /screenshots directory contains visual evidence of the successful deployment:

Pod Status: A screenshot showing both services in a Running state within the Minikube cluster.

Log Output: Proof of the terminal logs displaying the "Payment Service" and "Shipping Service" messages.

Created by: Kiran

Focus: DevOps Engineering & Kubernetes Learning