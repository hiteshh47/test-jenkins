pipeline {
    agent any
    stages {
        stage('Run shell') {
            steps {
                sh '''
                  docker build -t my-website:latest .
                  docker run -d --name my-website-app -p 8081:80 my-website
                  echo $BUILD_NUMBER
                '''
            }
        }
    }
}
