pipeline {
    agent { label 'slave'}

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                   }
        }
        stage('Deploy') {
            steps {
                script {
                kubernetesDeploy(configs: "deploy.yaml", kubeconfigId: "aws")
                }
            }
        }
    }
}
