pipeline {
    agent any

    

    stages {

                

        stage ('TF Initialize') {
            steps {
                sh "terraform init -input=false"
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
                sh "terraform apply -auto-approve"
            }
        }
    }
}
