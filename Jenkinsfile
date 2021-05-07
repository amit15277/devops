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
                    sh "sudo terraform/terraform workspace select dev || sudo terraform/terraform workspace new dev"
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
