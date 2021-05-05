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
                sh "terraform version && terraform fmt -recursive && terraform validate"
            }
        }

        
        stage ('Apply') {
            
            steps {
                sh "terraform apply -auto-approve"
            }
        }
    }
}
