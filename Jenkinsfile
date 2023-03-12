pipeline {
    agent any
    stages {
        stage('Run shell') {
            when{
                expression {
                    env.GIT_BRANCH =='origin/test'
                }
            
            }
            steps {
                sh '''
                  docker build -t my-website:latest .
                  docker run -d --name my-website-app-${BUILD_NUMBER} -p 8081:80 my-website
                  echo $BUILD_NUMBER
                '''
            }
        }
    }
}
