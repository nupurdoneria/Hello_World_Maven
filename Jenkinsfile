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
       //stage('Performance Test') {
         //  steps {
           //    script {
                    //sh "cd /var/lib/jenkins/apache-jmeter-5.3/bin"
             //       sh "/var/lib/jenkins/apache-jmeter-5.3/bin/jmeter.sh -n -t /var/lib/jenkins/apache-jmeter-5.3/bin/ThreadGroup.jmx -l Result.jtl"
               //}
           //}
       //}
       stage('Performance Test Build') {
           steps {
               build job: "Test_Performance", wait: true
           }
       }
    }
    
}
