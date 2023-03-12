pipeline {
    agent any
    stages {
        stage('Run shell') {
            when{
                expression {
                    env.GIT_BRANCH =='origin/main'
                }
            
            }
            steps {
                sh '''
                  docker image prune -f
                  docker rm -f $(docker ps -a -q) || true
                  aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 864231724929.dkr.ecr.us-east-1.amazonaws.com
                  docker build -t my-website:${BUILD_NUMBER} .
                  docker tag my-website:latest 864231724929.dkr.ecr.us-east-1.amazonaws.com/h-projects:${BUILD_NUMBER}
                  docker push 864231724929.dkr.ecr.us-east-1.amazonaws.com/h-projects:${BUILD_NUMBER}
                  
         
                  echo $BUILD_NUMBER
                '''
            }
        }
    }
}
