pipeline{
    agent{
        label "jenkins-agent"
    }
    tools{
        jdk 'java17'
        maven 'maven3'
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

        stage("Test Application"){
            steps{
                sh "mvn test"
            }
        }

        stage("SonarQube Analysis"){
            steps{
                script {
                    withSonarQubeEnv(credentialsId: 'sonar-token') {
                        sh "mvn sonar:sonar"
                    }
                }
            }   
        }

        stage("SonarQube Analysis"){
            steps{
                script {
                    waitForQualityGate abortPipeline: false, credentialsId: 'sonar-token'
                }
            }   
        }
    }
}