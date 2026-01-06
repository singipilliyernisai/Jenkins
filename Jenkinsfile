pipeline {
    agent any
    environment {
       image_name = "jenkins-docker-demo"
    }

    stages {
        stage('Checkout') {
            steps {
                echo "Code checked out"
                git branch: 'main', url:'https://github.com/singipilliyernisai/Jenkins.git'
            }
        }
        stage('docker building'){
            steps{
                echo "Building docker image"
                sh 'docker build -t $image_name .'
            }
        }

        stage('running the container') {
            steps {
                echo "running the docker container"
               sh '''
        docker rm -f demo_container || true
        docker run -d -p 8081:80 --name demo_container jenkins-docker-demo1
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
