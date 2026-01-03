pipeline {
    agent any
    environment {
        APP_NAME = "Pipeline- Practice"
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Code checked out'
                git branch: 'main', url:'https://github.com/singipilliyernisai/Jenkins.git'
            }
        }
        stage('show workspaces'){
            steps{
                echo"Listing workspaces"
                sh 'ls -l'
            }
        }

        stage('Build') {
            steps {
                echo "Build application:$APP_NAME"
                sh 'echobuild completed successfull'
            }
        }
    }
    post{
        success{
            echo"Pipeline completed successfully"
        }
        failure{
            echo"Pipeline failed"
        }
    }

}
