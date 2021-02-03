pipeline {
    agent any
   stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Deploy') {
            script {
                sh "cp webapp/target/webapp.war /usr/share/tomcat/webapp"
              
            }
        }
    }
    
}
