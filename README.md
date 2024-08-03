## Introduction to Kubernetes and the CKA Exam

Kubernetes, often abbreviated as K8s, is an open-source platform designed to automate the deployment, scaling, and operation of containerized applications. Originally developed by Google and now maintained by the Cloud Native Computing Foundation (CNCF), Kubernetes has become the de facto standard for container orchestration in the cloud computing world.

### What is Kubernetes?

Kubernetes simplifies the complex tasks involved in managing containerized applications. It provides a robust framework to run distributed systems resiliently, scaling and healing applications as needed. The platform offers several key features, including:

- **Automated Rollouts and Rollbacks:** Kubernetes ensures that applications are always running in the desired state and can automatically roll out changes and roll back if issues are detected.
- **Service Discovery and Load Balancing:** Kubernetes can expose containers using DNS names or their own IP addresses and balance the load across the containers.
- **Storage Orchestration:** Kubernetes allows you to automatically mount the storage system of your choice, whether from local storage, public cloud providers, or network storage solutions.
- **Self-Healing:** Kubernetes restarts containers that fail, replaces and reschedules containers when nodes die, kills containers that don’t respond to user-defined health checks, and doesn’t advertise them to clients until they are ready to serve.

### Certified Kubernetes Administrator (CKA) Exam

The Certified Kubernetes Administrator (CKA) exam is a performance-based certification that tests a candidate's ability to install, configure, and manage Kubernetes clusters. The CKA is designed for Kubernetes administrators, cloud administrators, and other IT professionals who manage Kubernetes instances. The exam covers a wide range of topics, including:

- **Cluster Architecture, Installation & Configuration:** Understanding Kubernetes architecture and components, setting up and configuring a Kubernetes cluster, and managing it using kubectl.
- **Workloads & Scheduling:** Managing deployments, pods, and other resources; understanding scheduling policies and mechanisms.
- **Services & Networking:** Configuring network access and policies; managing services and network endpoints.
- **Storage:** Implementing different storage solutions, persistent volumes, and persistent volume claims.
- **Troubleshooting:** Identifying and resolving issues within the Kubernetes cluster.

The CKA certification demonstrates that an individual has the skills, knowledge, and competence to perform the responsibilities of a Kubernetes administrator.

## Kubernetes and MariaDB WordPress Deployment

This repository contains the necessary configurations and files to deploy a WordPress application with a MariaDB database on a Kubernetes cluster. The deployment is designed to be simple and easy to use, leveraging Kubernetes resources such as Pods, Services, Deployments, and Persistent Volume Claims to manage the application.

### Deployment Overview

The deployment consists of two main components:

1. **MariaDB:** A popular open-source relational database management system, used as the backend database for WordPress.
2. **WordPress:** The world’s most popular content management system (CMS), used for building websites and blogs.

### Repository Structure

- **/k8s:** Contains the Kubernetes manifests for deploying WordPress and MariaDB.
  - **mariadb-deployment.yaml:** Defines the Deployment and Service for MariaDB.
  - **wordpress-deployment.yaml:** Defines the Deployment and Service for WordPress.
  - **persistent-volume.yaml:** Contains the PersistentVolume and PersistentVolumeClaim definitions for both MariaDB and WordPress.

### How to Deploy

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/your-repo.git
   cd your-repo/k8s
   ```

2. **Apply the Persistent Volume and Claims:**
   ```bash
   kubectl apply -f persistent-volume.yaml
   ```

3. **Deploy MariaDB:**
   ```bash
   kubectl apply -f mariadb-deployment.yaml
   ```

4. **Deploy WordPress:**
   ```bash
   kubectl apply -f wordpress-deployment.yaml
   ```

5. **Access WordPress:**
   Once the deployments are complete, you can access the WordPress application by retrieving the external IP address of the WordPress service:
   ```bash
   kubectl get svc
   ```

   Navigate to the IP address in your web browser to complete the WordPress setup.

### Conclusion

This deployment provides a simple and efficient way to run a WordPress site with a MariaDB backend on Kubernetes. By following the steps outlined in this README, you can quickly set up and manage your WordPress site, leveraging the power and flexibility of Kubernetes.

Feel free to contribute to this project by submitting issues or pull requests. Your feedback and contributions are highly appreciated.
