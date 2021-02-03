pipeline {
    agent any
   stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Deploy') {
            steps {
                sshagent(['abc123xyz']) {
                   sh "cp -o StrictHostKeyChecking=no webapp/target/webapp.war /usr/share/tomcat/webapp"
            }
                    
            }
        }
    }
    
}
