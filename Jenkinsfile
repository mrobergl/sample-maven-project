
pipeline {
    agent any
    
    stages {
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
