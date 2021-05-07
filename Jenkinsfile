pipeline {
    agent any

    

    stages {

        

        stage ('TF Initialize') {
            steps {
                sh "/terraform/Amitdevops/INFRA/terraform init -input=false"
            }
        }

        stage ('Pre Checks') {
            
            steps {
                script {
                    sh "/terraform/Amitdevops/INFRA/terraform workspace select dev || /terraform/Amitdevops/INFRA/terraform workspace new dev"
                }
            }
        }

        
        stage ('Apply') {
            
            steps {
                sh "/terraform/Amitdevops/INFRA/terraform plan"
            }
        }
    }
}
