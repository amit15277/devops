pipeline {
    agent any

    

    stages {

        

        stage ('TF Initialize') {
            steps {
                sh "/terraform/Amitdevops/INFRA/terraform init -input=false ./jenkins"
            }
        }

        stage ('Pre Checks') {
            
            steps {
                script {
                    sh "/terraform/terraform workspace select dev || /terraform/terraform workspace new dev"
                }
            }
        }

        
        stage ('Apply') {
            
            steps {
                sh "/terraform/terraform apply -auto-approve ./jenkins"
            }
        }
    }
}
