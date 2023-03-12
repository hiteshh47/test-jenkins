pipeline {
    agent any
    stages {
        stage('Run shell') {
            steps {
                sh '''
                  echo $BUILD_NUMBER
                  echo $JOB_NAME
                  echo $NODE_NAME
                '''
            }
        }
    }
}
