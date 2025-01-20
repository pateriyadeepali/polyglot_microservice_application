# BookInfo Application Deployment on Kubernetes

## Introduction  
The **BookInfo Application** is a sample polyglot application deployed on Kubernetes to showcase modern DevOps practices. The application is composed of **five pods**:  
- **Product Page Pod**: Displays information about the product (e.g., a book).  
- **Three Reviews Pods**: Provides user reviews for the product, each version having different functionalities (e.g., one with no stars, another with black stars, and the last with red stars).  
- **Details Pod**: Displays additional product details.

This deployment highlights the integration of multiple tools and technologies for managing, monitoring, and scaling applications seamlessly.  

---

## Prerequisites  
To deploy this application, you will need:  
- A **Minikube Cluster** for setting up a local Kubernetes cluster (recommended for development and testing).  
- Alternatively, **Amazon EKS (Elastic Kubernetes Service)** can be used for production-grade setups.  

---

## Source Code  
The source code for the **BookInfo Application** is available at my GitHub repository:  
[BookInfo Application Source Code](https://github.com/pateriyadeepali/bookinfo.git)  

---

## Tools and Technologies Used  

### 1. **Kubernetes**  
Kubernetes serves as the backbone of this deployment, orchestrating the pods and managing their lifecycle, scalability, and communication.  

### 2. **Minikube**  
Used to set up a local Kubernetes cluster for development and testing.  

### 3. **ArgoCD**  
Implemented GitOps workflows to automate continuous deployment directly from the source repository to the Kubernetes cluster.  

### 4. **Istio**  
Configured as the service mesh for advanced traffic management, load balancing, and secure communication between the pods.  

### 5. **Kiali**  
Visualized service dependencies, traffic flow, and health of the deployed microservices in the Istio service mesh.  

### 6. **Prometheus**  
Enabled real-time monitoring of metrics such as CPU usage, memory consumption, and pod availability.  

---

## Workflow Diagram  
The following diagram illustrates the flow of tools and technologies used in this project:  

![Workflow Diagram]("C:\Users\pater\Downloads\workflow.diagram1.drawio.png")  




