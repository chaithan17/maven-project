pipeline {
    agent any
   
    stages{
        stage('Build'){
            steps {
                bat 'mvn clean package'
            }
            post {
                success {
                    echo 'test my Archiving...'
                    archiveArtifacts artifacts: '**\target\*.war'
                }
            }
        }
        stage ('Deploy to staging'){
            steps {
                build job: 'deploy-to-staging'
            }
        }

    }
}
