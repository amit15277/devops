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
                    sh "terraform workspace select demo || terraform workspace new demo"
                }
            }
        }

        
        stage ('Apply') {
            
            steps {
                sh "terraform plan"
            }
        }
    }
}
