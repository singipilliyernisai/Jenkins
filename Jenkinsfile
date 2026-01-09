tpipeline {
    agent any
    environment {
      DOCKERHUB_USERNAME = "yernisai"
        IMAGE_NAME = "jenkins-nginx-demo"
        IMAGE_TAG = "latest"
    }
    stages {
        stage('Checkout') {
            steps {
                echo "Code checked out"
                git branch: 'main', url:'https://github.com/singipilliyernisai/Jenkins.git'
            }
        }
        stage('k8s building'){
            steps{
                echo "Building k8s image"
                sh '''
                kubectl apply -f k8s/deployment.yaml
                kubectl apply -f k8s/service.yaml
                '''
            }
        }

    
    }
    post{
        success{
            echo "docker container completed"
        }
        failure{
            echo "not completed docker container"
        }
    }

}
