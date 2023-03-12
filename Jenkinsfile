pipeline {
    agent any
    stages {
        stage('Run shell') {
            steps {
                sh '''
                  docker pull httpd
                  echo $JOB_NAME
                  echo $NODE_NAME
                '''
            }
        }
    }
}
