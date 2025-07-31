# Java_calculator_app
  1.Cloned the Git Repository
  
The Java web application source code was cloned from a GitHub repository to prepare it for build and deployment.

 2.Wrote Configuration Files
 
Created a Dockerfile to containerize the Java application. Also created Kubernetes deployment.yaml and service.yaml files for deploying the application into a Kubernetes cluster.

3.  Installed and Configured Jenkins

Jenkins was installed as the CI/CD automation server. Essential plugins such as:
•	Pipeline

•	Docker Pipeline

•	Stage View

•	Maven Integration

•	Git
were installed to support build and deployment stages.

4.Set Up Maven and Docker in Jenkins

Configured Maven and Docker tools inside Jenkins global tool configuration to be used within pipelines.

5. Created Kops Kubernetes Cluster

A Kubernetes cluster was created using Kops on AWS. An S3 bucket was used as the state store for the cluster.

6. Configured Jenkins Credentials

The following credentials were securely added in Jenkins:
•	DockerHub username/password for image push (DockerHub-Credentials)

•	AWS IAM access key and secret (aws-creds)

•	Kubeconfig file to authenticate with the Kubernetes cluster (kubeconfig)

7.Prepared Jenkins Agent/Node

The Jenkins agent (build node) was configured with:

•	Docker (for image build and run)

•	AWS CLI (for accessing AWS services)

•	Kubectl (for deploying to Kubernetes)

•	Kops (for managing the Kubernetes cluster)

8. CI/CD Pipeline Execution

A Jenkins pipeline (Jenkinsfile) was created to automate the following stages:

•	Code Checkout from GitHub

•	Maven Build to compile the Java application

•	Docker Build & Push to DockerHub

•	Kubernetes Deployment using kubectl

9. Application Deployment and Access

•	The application was deployed in the Kops-managed Kubernetes cluster using kubectl apply.

•	A NodePort service exposed the application on a public EC2 node's IP address.

•	The application was accessed via http://<NodeIP>:<NodePort>.

•	It was also verified locally using docker run to ensure the container worked as expected.
