pipeline {
    agent { label 'slave'}

    stages {
        stage('Build') {
            steps {
                sh """
                    aws --version
                    kubectl
                    cat ~/.kube/config 
                """
                   }
        }
        stage('Deploy') {
            steps {
                script {
                kubernetesDeploy(configs: "deploy.yaml", kubeconfigId: "aws",enableConfigSubstitution: false)
                }
            }
        }
    }
}
