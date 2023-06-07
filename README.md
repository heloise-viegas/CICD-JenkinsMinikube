# CICD-JenkinsMinikube

## Install jenkins on Ubuntu 
https://www.digitalocean.com/community/tutorials/how-to-install-jenkins-on-ubuntu-22-04

## Install Minikube on Ubuntu
https://minikube.sigs.k8s.io/docs/start/

Steps:
1. Start Minikube cluster:   minikube start
2. Start jenkins service:    service jenkisn start
3. Open jenkins url in browser i.e. localhost:8080
4. Install Kubectl plugin in jenkins
5. Create the jenkinsfile with only the Git checkout stage. Commit this file to your git repository.
6. Create a pipeline in jenkins and connect it to the git repo with the jenkinsfile.(Add required git ssh keys etc)
7. Save and build the pipeline, to test the git checkout phase.
8. For Jenkins to communicate with the Minikube cluster, we can edit he minikube config file at ~/.kube/config
9. Replace the following in the config file: certificate-authority with certificate-authority-data and the value will be at /home/user/.minikube/ca.crt| base64 -w 0; echo
10. Similarly for client-certificate & client-key, the key path will be mentioned as the value. Save the config file.
11. Under Jenkins>Mange Credentials add the config file and save.![image](https://github.com/heloise-viegas/CICD-JenkinsMinikube/assets/37453877/99be82aa-19ee-4e9e-ab5a-df94ffd148eb)
12. Go to configure pipeline and click on Pipeline syntax,this will redirect to a new screen.
13. Add the following details and click on Generate script.![image](https://github.com/heloise-viegas/CICD-JenkinsMinikube/assets/37453877/71969ae0-068f-4b49-8c8c-03b1f777ec95)
![image](https://github.com/heloise-viegas/CICD-JenkinsMinikube/assets/37453877/22cbebc9-0442-457b-beff-034de099eb2c)
14. Copy the script into the Jenkinsfile stage ![image](https://github.com/heloise-viegas/CICD-JenkinsMinikube/assets/37453877/6dbffabe-327b-4bc6-8d7f-0144a6b1e949)
15. Add any kubectl command to test or deploy a sample pod on the cluster.
16. Save and commit the jenkinsfile.
17. Build the pipeline and verify if the commands executed correctly.
