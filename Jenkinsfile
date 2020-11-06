pipeline {
    agent { label 'slave'}

    stages {
        stage('Build') {
            steps {
                sh """
                    aws --version
                    kubectl
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
