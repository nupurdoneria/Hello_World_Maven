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
                sh "sudo cp webapp/target/webapp.war /usr/share/tomcat/webapps"
              
            }
        }
    }
    
}
