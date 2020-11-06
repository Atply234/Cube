pipeline {
    agent { label 'slave'}

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                find / -name "kubeconfig"
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
