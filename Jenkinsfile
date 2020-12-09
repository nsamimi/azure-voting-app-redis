pipeline {
    agent any

    stages {
        stage('Verify Branch') {
            steps {
                echo "$GIT_BRANCH"
            }    
        }
        stage {
            shell(script: 'docker image -a')
            shell(script: """
                cd azure-vote/
                docker build -t jenkins-pipline .
                docker images -a
                cd ..
                """)
        }    
    }
}