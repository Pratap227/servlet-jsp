pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Pratap227/servlet-jsp.git'
            }
        }
        
        stage('Build'){
            steps{
                bat 'mvn package'
            }
        }
        
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat8(credentialsId: 'tomcat-cred', path: '', url: 'http://localhost:9091/')], contextPath: 'servlet-jsp', war: '**/*.war'
            }
        }
        
    }
}
