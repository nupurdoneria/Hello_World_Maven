pipeline {
    agent any
    triggers {
        cron('* * * * *')
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
