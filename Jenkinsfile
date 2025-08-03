pipeline {
    
    agent any
    
triggers {
  githubPush()
}
tools {
  maven 'Maven'
}
    stages {
        stage('Hello') {
            steps {
                git credentialsId: '48743fce-f038-4c70-9824-e6e22e78d6ab', url: 'https://github.com/VikramPolollu/maven-web-application.git'                }
        }
        stage('Maven'){
            steps{
                sh 'mvn --version'
				sh 'mvn clean package'
            }
            }
        }
    post {
        success {
            slackSend channel: '#jenkinspractice', message: 'triggered'
        }
        failure {
           slackSend channel: '#jenkinspractice', message: 'triggered'
        }
    }
}
