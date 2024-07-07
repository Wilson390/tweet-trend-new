pipeline {
    agent {
        node {
            label 'maven'
        }
    }

    environment {
       PATH = "/opt/apache-maven-3.9.8/bin:$PATH"
    }

    tools {
        jdk 'JDK 11' // Ensure this matches the name you gave JDK 11 in Global Tool Configuration
    }

    stages {
        stage('build') {
            steps {
                sh 'mvn clean deploy'
            }
        }

        stage('SonarQube Analysis') {
            environment {
                scannerHome = tool 'wilsondt390-sonar-scanner'
            }
            steps{
                withSonarQubeEnv('wilsondt390-sonarqube-server'){
                    sh "${scannerHome}/bin/sonar-scanner"
                }
            }

        }
    }
}

