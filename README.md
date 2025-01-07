# Three-Tier Application on AWS EKS Managed Kubernetes Service

## 🚀 Project Overview

This project demonstrates the deployment of a highly scalable **Three-Tier Architecture** application on **Amazon Elastic Kubernetes Service (EKS)**. The application is structured into three tiers:

1. **Frontend Tier**: A user-facing web application (e.g., React, Angular, or Vue.js).
2. **Backend Tier**: A REST API or service layer (e.g., Node.js, Python Flask, or Java Spring Boot).
3. **Database Tier**: A robust database service (e.g., Amazon RDS, DynamoDB, or a self-managed database on Kubernetes).

This architecture ensures scalability, reliability, and security while leveraging AWS-managed services for ease of maintenance.

---

## 📋 Prerequisites

Before setting up this project, ensure you have the following:

1. **AWS Account**: An active AWS account with permissions to create resources (EKS, VPC, RDS, etc.).
2. **AWS CLI**: Installed and configured with credentials. [Download AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
3. **kubectl**: Kubernetes command-line tool installed. [Install kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
4. **eksctl**: CLI to create and manage EKS clusters. [Install eksctl](https://eksctl.io/)
5. **Helm**: Kubernetes package manager. [Install Helm](https://helm.sh/docs/intro/install/)
6. **IAM Role Permissions**: Ensure your IAM user/role has permissions to create and manage EKS resources.

---

## 🛠️ Project Setup Instructions

Follow these steps to deploy the Three-Tier Application:

### 1. 🏗️ Create an EKS Cluster

1. Create a Kubernetes cluster using `eksctl`:
   ```bash
   eksctl create cluster \
     --name three-tier-cluster \
     --region <your-region> \
     --nodegroup-name standard-nodes \
     --node-type t3.medium \
     --nodes 2 \
     --nodes-min 1 \
     --nodes-max 3 \
     --managed
   ```
2. Verify the cluster:
   ```bash
   kubectl get nodes
   ```

### 2. 🔧 Deploy the Application

1. Clone the repository:
   ```bash
   git clone https://github.com/334yash/Three-Tier-Application-on-AWS-EKS-Managed-Kubernetes-Service.git
   cd Three-Tier-Application-on-AWS-EKS-Managed-Kubernetes-Service
   ```

2. Deploy the **Database Tier**:
   - Apply the database manifest file (e.g., using Amazon RDS or a MySQL Pod):
     ```bash
     kubectl apply -f manifests/database-tier.yaml
     ```
   - Confirm the database service is running:
     ```bash
     kubectl get svc
     ```

3. Deploy the **Backend Tier**:
   - Apply the backend service manifest file:
     ```bash
     kubectl apply -f manifests/backend-tier.yaml
     ```
   - Verify the backend pod and service are running:
     ```bash
     kubectl get pods
     kubectl get svc
     ```

4. Deploy the **Frontend Tier**:
   - Apply the frontend deployment and service:
     ```bash
     kubectl apply -f manifests/frontend-tier.yaml
     ```
   - Check the frontend service (usually a LoadBalancer):
     ```bash
     kubectl get svc
     ```

### 3. 🌐 Access the Application

1. Retrieve the public IP or DNS of the LoadBalancer:
   ```bash
   kubectl get svc -n default
   ```
2. Open the URL in your browser to access the application.

---

## 🛡️ Security Best Practices

1. Use **IAM Roles for Service Accounts (IRSA)** to manage permissions securely.
2. Enable **encryption** for the database tier using AWS KMS.
3. Configure **Network Policies** to restrict communication between tiers.
4. Use **AWS WAF (Web Application Firewall)** to protect the frontend.
5. Regularly apply Kubernetes security updates and patches.

---

## 📊 Architecture Diagram

Below is a high-level architecture diagram of the Three-Tier Application:

```plaintext
                +----------------+
                |  Frontend Tier |
                | (React/Angular)|
                +--------+-------+
                         |
                         v
                +----------------+
                |  Backend Tier  |
                | (Node.js API)  |
                +--------+-------+
                         |
                         v
                +----------------+
                | Database Tier  |
                | (Amazon RDS)   |
                +----------------+
```

---

## 📦 Project Structure

```plaintext
three-tier-application-on-eks/
├── manifests/
│   ├── frontend-tier.yaml      # Frontend Deployment and Service
│   ├── backend-tier.yaml       # Backend Deployment and Service
│   └── database-tier.yaml      # Database Deployment and Service
├── scripts/                    # Helper scripts
├── README.md                   # Project documentation
└── .gitignore                  # Git ignore file
```

---

## 🤝 Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

---

## 📜 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## 📞 Support

If you face any issues, please open an issue in this repository or reach out to the maintainer.

---

## 💡 Highlights

- **Automated Scaling**: Leveraging EKS-managed worker nodes.
- **Load Balancer Integration**: AWS ALB automatically routes traffic.
- **Cost-Effective**: Uses managed AWS services to reduce operational overhead.
- **Cloud-Native**: Fully Kubernetes-based deployment for portability.

---

### Enjoy building your scalable and robust Three-Tier Application on AWS EKS! 🌐
