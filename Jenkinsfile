
pipeline {
    agent{
            label "Slave2"
        }
        tools {
            maven 'maven'
            //jdk 'jdk'
        }
    stages {

        stage('Testing') {
            steps {
                echo 'Testing the application...'
                sh "mvn clean test"
            }
        }
    }
    post {
        success{
        echo "Testing stage successful"
        }
        failure{
        echo "Testing stage failed"
        }
    }
}
