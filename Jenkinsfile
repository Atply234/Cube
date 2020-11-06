pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Deploy') {
            steps {
                script {
                kubernetesDeploy(configs: "deploy.yaml", kubeconfigId: "sedd")
                }
            }
        }
    }
}
