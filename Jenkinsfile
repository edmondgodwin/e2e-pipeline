pipeline{
    agent{
        label "jenkins-agent"
    }
    stages{
        stage("Clean Workspace"){
            steps{
                cleanWs()
            }
        }

        stage("Checkout from SCM"){
            steps{
                git branch: 'master', url: 'https://github.com/edmondgodwin/e2e-pipeline.git'
            }
        }

        stage("Build Application"){
            steps{
                sh "mvn clean package"
            }
        }
    }
}