pipeline {
    agent any
    triggers { pollSCM('* * * * *') }
   stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Deploy') {
            steps {
                sh "cp webapp/target/webapp.war /usr/share/tomcat/webapps"
              
            }
        }
    }
    
}
