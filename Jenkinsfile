
pipeline {
    agent any
    
    stages {
        stage('checkout') {
            steps {
                git branch:'main', url: 'https://github.com/mrobergl/sample-maven-project.git'   
            }
        }
        
        stage('build') {
            steps {
                sh '/usr/share/maven/bin/mvn package'   
            }
        }
    
        stage('capture') {
            steps {
                archiveArtifacts artifacts: '**/target/*.jar'
                jacoco()   
            }
        }
    }
    
    post {
        always {
            sh 'echo "Hello Elaheh"'
        }
    }
}
