
## ✅ Deployed a scalable Three-tier application on AWS EKS (Kubernetes).

[Documentation](https://linktodocumentation)




**# Scalable Three-tier Application on AWS EKS**

This project demonstrates the deployment of a scalable three-tier application on Amazon Elastic Kubernetes Service (EKS). It leverages containerization with Docker for the front-end, back-end, and database, along with Kubernetes for orchestrated container management and AWS Application Load Balancer (ALB) for efficient traffic distribution.

**## Project Overview**

This application showcases the following key capabilities:

- **Scalability:** The application can be easily scaled horizontally by adding more instances of containers to meet increased demand.
- **Resilience:** The use of containers and Kubernetes ensures that the application can tolerate failures by restarting failed containers.
- **Security:** Security best practices have been incorporated to protect the application from potential vulnerabilities.

**## Technologies Used**

- **AWS EKS (Kubernetes):** Container orchestration platform for managing containerized applications.
- **Docker:** Containerization technology for packaging and deploying applications.
-  **Node.js:** JavaScript runtime environment for the back-end.
- **MongoDB:** NoSQL document database for data persistence.
- **AWS ALB:** Load balancing service to distribute traffic across multiple instances of your application.

**## Architecture**

The application consists of three tiers:

1. **Front-end (ReactJS):** This tier delivers the user interface and interacts with the back-end API.
2. **Back-end (Node.js):** This tier handles business logic, API requests, and communication with the database.
3. **Database (MongoDB):** This tier stores application data persistently.

Each tier is containerized using Docker and deployed as a Kubernetes deployment. The ALB distributes traffic across multiple instances of the back-end containers.

**## Deployment Steps**

**1. Setting Up AWS Environment**

- Create an AWS account if you don't have one already.
- Configure AWS CLI or use the AWS Management Console to set up the necessary resources:
    - VPC (Virtual Private Cloud)
    - EKS Cluster
    - IAM Roles for service accounts

**2. Dockerizing the Application**

- Create Dockerfiles for each tier (front-end, back-end, database) defining the build process and environment variables.
- Build Docker images using `docker build` for each tier.

**3. Deploying to EKS**

- Configure Kubernetes deployments and services for each tier's containerized application.
- Use `kubectl apply` to deploy the application resources to the EKS cluster.

**4. Integrating AWS ALB**

- Create an ALB in your VPC and configure listeners and target groups to route traffic to the back-end service.

**5. Communication and Data Persistence**

- Ensure proper communication between tiers by defining service discovery mechanisms in Kubernetes.
- Configure MongoDB connection details and data persistence mechanisms in the back-end.

**## Scalability and Security Considerations**

- Implement scaling strategies in Kubernetes (e.g., HPA - Horizontal Pod Autoscaler) for automatic scaling based on resource utilization or demand.
- Follow security best practices:
    - Use secrets management for sensitive information.
    - Implement least privilege principles for container access.
    - Regularly scan for vulnerabilities and update dependencies.

**## Running the Application Locally**

1. Install Docker locally.
2. Build the Docker images for each tier using `docker build` commands.
3. Run the containers using `docker run` commands with appropriate port mappings.
4. Configure environment variables for each container (database connection, API URLs, etc.).
5. Access the application's front-end URL in your browser.

**## Additionally**

- Using infrastructure as code (IaC) tools like Terraform or AWS CloudFormation for automating infrastructure provisioning.
- Implement continuous integration/continuous delivery (CI/CD) pipelines for automated deployments and testing.



**## Contributing**

If you'd like to contribute to this project, please create pull requests. We welcome bug fixes, improvements, and new features.

