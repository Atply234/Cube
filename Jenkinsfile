pipeline {
    agent { label 'slave'}

    stages {
        stage('Build') {
            steps {
                sh """
                    aws --version
                    apt-get update &&  apt-get install -y apt-transport-https gnupg2 curl
                    curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg |  apt-key add -
                    echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" |  tee -a /etc/apt/sources.list.d/kubernetes.list
                    apt-get update
                    apt-get install -y kubectl
                    kubectl
                """
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
