pipeline {
    agent any
    triggers {
        cron('H/2 * * * *')
    }
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
