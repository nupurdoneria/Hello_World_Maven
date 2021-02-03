pipeline {
    agent any
    tools { 
        maven 'Maven 3.0.5' 
        jdk 'jdk8' 
    }
    stages {
        stage ('Initialize') {
            steps {
                sh echo "PATH = ${PATH}"
                sh echo "M2_HOME = ${M2_HOME}"
            }
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -f pom.xml clean install package' 
            }
        }

   }
}
