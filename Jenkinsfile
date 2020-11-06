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
                kubernetesDeploy(configs: "deploy.yaml", kubeconfigId: "b22ad5cc-40af-4d32-a884-b684df89298a")
                }
            }
        }
    }
}
