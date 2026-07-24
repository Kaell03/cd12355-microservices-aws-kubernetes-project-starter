Coworking Space Analytics Service on Amazon EKS
This project deploys a containerized analytics application and PostgreSQL database on Amazon Elastic Kubernetes Service (EKS). The application was built as a Docker image, pushed to Amazon Elastic Container Registry (ECR), and deployed using Kubernetes manifests. Configuration settings are managed through Kubernetes ConfigMaps and Secrets. Persistent storage is configured for the PostgreSQL database using Persistent Volumes and Persistent Volume Claims.
Components

Amazon EKS Cluster
Amazon ECR Repository
PostgreSQL Database
Analytics Application
Kubernetes Deployments
Kubernetes Services
ConfigMap
Secret
Persistent Volume (PV)
Persistent Volume Claim (PVC)

Deployment Validation
The deployment was successfully validated through:

Healthy EKS cluster status
Running PostgreSQL pod
Running Analytics application pod
Kubernetes services exposed successfully
Successful API responses from the analytics endpoints
ECR image repository containing the deployed container image

Notes on CloudWatch
CloudWatch Container Insights was not enabled in the provided AWS lab environment. Application health was verified through Kubernetes logs, which showed successful health-check requests and normal application operation without errors.
Notes on CodeBuild
An attempt was made to configure AWS CodeBuild with GitHub integration and webhook-triggered builds. However, the AWS lab role provided by the learning environment does not allow GitHub CodeConnections operations such as codeconnections:StartOAuthHandshake and codeconnections:ListConnections. Because of this restriction, GitHub authorization could not be completed and the CodeBuild pipeline could not access the repository. Screenshots of the permission errors are included as supporting evidence.
Repository Contents

analytics/ – Analytics application source code
deployment/ – Kubernetes manifests
db/ – Database schema and seed scripts
buildspec.yml – AWS CodeBuild configuration
README.md – Project documentation

Deployment Status
The application and database are successfully deployed and running on Amazon EKS. Kubernetes deployments, services, ConfigMaps, Secrets, and persistent storage configurations are functioning correctly.CodeBuild webhook trigger
Webhook test
Webhook test Fri Jul 24 20:59:01 UTC 2026
