pipeline {
    agent none
    stages {
        stage('Deploy') {
            agent any
            steps {
                withAWS(region:'ap-southeast-1',credentials:'aws-credential') {
                    sh "aws eks update-kubeconfig --name devops-cluster"
                    sh "kubectl create ns eks-ns"
                    sh "kubectl config set-context --current --namespace eks-ns"
                    sh "kubectl apply -f backend.yaml"
                    sh "kubectl apply -f frontend.yaml"
                }
            }
        }
    }
}
