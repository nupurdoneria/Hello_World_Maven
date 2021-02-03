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
       stage('Performance Test') {
           steps {
               sh "/var/lib/jenkins/apache-jmeter-5.3/bin jmeter -n -t /home/necuser/"Thread Group.jmx" -l /home/necuser/Result.jtl"
           }
       }
    }
    
}
