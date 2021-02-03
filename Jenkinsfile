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
                sshagent(['ssh_server_username']) {
                   sh "scp -o StrictHostKeyChecking=no webapp/target/webapp.war necuser@10.0.96.44:/usr/share/tomcat/webapp"
            }
                    
            }
        }
    }
    
}
