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

## How to Deploy the Application  

### Step 1: Set Up Kubernetes Cluster 
1. Install **Minikube** on your system. Follow the [Minikube documentation](https://minikube.sigs.k8s.io/docs/start/) for installation.  
2. Start Minikube:  
   ```bash
   minikube start

### Step 2: Deploy the BookInfo Application
1. Clone the repository:

git clone https://github.com/pateriyadeepali/bookinfo.yml
cd bookinfo.yml

2. Apply the Kubernetes:
 kubectl apply -f bookinfo.yml

 kubectl port-forward svc productpage 80:9080

##########################################################################

####################### GitOps ##########################################

kubectl create namespace argocd kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

kubectl config set-context --current --namespace=argocd
https://github.com/argoproj/argo-cd/releases

argocd login --core or cd Downloads ./argocd-windows-amd64.exe login --core

argocd admin initial-password -n argocd or ./argocd-windows-amd64.exe admin initial-password -n argocd

kubectl port-forward svc/argocd-server -n argocd 8080:443

kubectl port-forward svc/productpage -n default 80:9080

#############################################################################

#################################### Istio ##################################

https://github.com/istio/istio/releases/tag/1.24.2

istioctl install --set profile=demo

kubectl get pods -n istio-system

kubectl get svc -n istio-system

kubectl label namespace default istio-injection=enabled

kubectl delete pods --all -n default

kubectl get pods -n default

curl https://github.com/pateriyadeepali/polyglot_microservice_application/blob/main/bookinfo-gateway.yaml -o bookinfo-gateway.yaml

git add . git commit -m first . git push

########################################### Kiali ################################

visit addon file inside istioctl and apply 
kubectl.exe apply -f addons/

istioctl dashboard kiali





