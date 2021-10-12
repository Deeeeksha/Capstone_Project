pipeline{
    agent{
        label "Slave2"
    }
    tools { 
        maven 'maven' 
        jdk 'jdk 8'
    }
    stages{
        stage("building"){
            steps{
                sh "mvn clean package"
            }
        }

    }
    post{
        always{
            mail to: 'deeksha.tripathi@knoldus.com',
			subject: "Pipeline: ${currentBuild.fullDisplayName} is ${currentBuild.currentResult}",
			body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}\n More info at: ${env.BUILD_URL}"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
