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
               cd apache-jmeter-5.3/bin
               jmeter -Jjmeter.save.saveservice.output_format=xml
               -n -t /home/necuser/"Thread Group.jmx"
               -l /home/necuser/Result.jtl
           }
       }
    }
    
}
