pipeline {
    agent any
    stages {
        stage('Build') {
            when{
                branch 'master'
            }
            steps {
                sh 'mvn package'
            }
        }
        stage('Test') {
          when{
            branch 'test'
          }
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                sh 'echo "Deploy code"'
            }
        }
    }
}
