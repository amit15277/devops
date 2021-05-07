pipeline {
    agent any

    

    stages {

        stage('git clone') {
            steps {
                sh 'sudo rm -r *;sudo git clone https://github.com/amit15277/devops.git'
            }
        }       

        stage ('TF Initialize') {
            steps {
                sh "sudo /terraform/terraform init -input=false ./jenkins"
            }
        }

        stage ('Pre Checks') {
            
            steps {
                script {
                    sh "terraform workspace select dev || terraform workspace new dev"
                }
            }
        }

        
        stage ('Apply') {
            
            steps {
                sh "sudo terraform/terraform apply -auto-approve ./jenkins"
            }
        }
    }
}
