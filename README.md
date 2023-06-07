# CICD-JenkinsMinikube

## Install jenkins on Ubuntu 
https://www.digitalocean.com/community/tutorials/how-to-install-jenkins-on-ubuntu-22-04

## Install Minikube on Ubuntu
https://minikube.sigs.k8s.io/docs/start/

Steps:
1. Start Minikube cluster   minikube start
2. Start jenkins service    service jenkisn start
3. Open jenkins url in browser i.e. localhost:8080
4. Install Kubectl plugin in jenkins
5. Create the jenkinsfile with only the Git checkout stage. Commit this file to your git repository.
6. Create a pipeline in jenkins and connect it to the git repo with the jenkinsfile.(Add required git ssh keys etc)
7. Save and build the pipeline, to test the git checkout phase.
8. Now we need Jenkins to communicate with the Minikube cluster, for this create Kubernetes SA, RBAC etc. https://github.com/heloise-viegas/CICD-JenkinsMinikube/blob/main/YAML/account.yaml
9. Click on Pipeline syntax inside the Jenkiisn pipeline, this will redirect to a new page
10. Add the following details and click on Generate script. ![image](https://github.com/heloise-viegas/CICD-JenkinsMinikube/assets/37453877/fa08f149-5da2-463c-be57-34834b2a1317)
![image](https://github.com/heloise-viegas/CICD-JenkinsMinikube/assets/37453877/e22c46b0-5e4d-4263-8876-9d0bf625f0bc)
11. Copy the script into the Jenkinsfile stage ![image](https://github.com/heloise-viegas/CICD-JenkinsMinikube/assets/37453877/d0e36dc6-1756-4b29-b582-61366ef355fb)

