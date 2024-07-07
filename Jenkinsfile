pipeline {
    agent {
        node {
            label 'maven'
        }
    }

envirnoment{
   PATH = "/opt/apache-maven-3.9.8/bin/bin:$PATH"
}
    stages {
        stage('build') {
            steps {
                sh 'mvn clean deploy'
            }
        }
    }
}

