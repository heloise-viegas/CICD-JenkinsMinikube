pipeline{
    agent any
    stages{
        stage("Checkout Code from Git"){
            steps{
                git(
                    url: "https://github.com/heloise-viegas/CICD-JenkinsMinikube.git",
                    branch: "main",
                    //credentialsId: "REPO_CREDENTIAL_ID_IN_JENKINS",
                   // changelog: true,
                   // poll: true
)
            }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========A executed successfully========"
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }

        stage("Build DockerImage"){
            steps{
               //dir('cd /var/lib/jenkins/workspace/CICD-Minikube/awesome-compose')
                dir('/var/lib/jenkins/workspace/CICD-Minikube/awesome-compose/aspnet-mssql/app')
                {
                       sh 'pwd'
                       sh 'docker build -t demoasp:latest .'
                }
            }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========A executed successfully========"
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }

        stage("Test"){
            steps{
                echo "========executing A========"
            }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========A executed successfully========"
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }

        stage("Push To Image Repo"){
            steps{
                echo "========executing A========"
            }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========A executed successfully========"
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }

        stage("Deploy on kubernetes"){
            steps{
            //   sh 'kubectl get pods'
          
             withKubeConfig(caCertificate: '',
                            clusterName: 'minikube', 
                            contextName: 'minikube', 
                            credentialsId: 'kubeconfig', 
                            namespace: 'default', 
                            restrictKubeConfigAccess: false, 
                            serverUrl: 'https://127.0.0.1:32769') {
                    sh 'kubectl get pods'
                    }   
                 }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========A executed successfully========"
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }
    }
    
}
