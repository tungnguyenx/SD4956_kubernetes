pipeline {
    agent none
    stages {
        stage('Deploy') {
            agent any
            steps {
                withAWS(region:'ap-southeast-1',credentials:'aws-credential') {
                    sh "aws eks update-kubeconfig --name devops-cluster"
                    sh "kubectl get nodes"
                }
            }
        }
    }
}
