pipeline{
    agent{
        label "jenkins-agent"
    // }
    // tools{
    //     jdk 'java17'
    //     maven 'maven3'
    // }
    // environment {
    //     APP_NAME = "complete-e2e-pipeline"
    //     RELEASE = "1.0.0"
    //     DOCKER_USER = "hdrc"
    //     DOCKER_PASS = 'docker-pass'
    //     IMAGE_NAME = "${DOCKER_USER}" + "/" + "${APP_NAME}"
    //     IMAGE_TAG = "${RELEASE}-${BUILD_NUMBER}"
    // }    
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

        // stage("Build Application"){
        //     steps{
        //         sh "mvn clean package"
        //     }
        // }

        // stage("Test Application"){
        //     steps{
        //         sh "mvn test"
        //     }
        // }

        // stage("SonarQube Analysis"){
        //     steps{
        //         script {
        //             withSonarQubeEnv(credentialsId: 'sonar-token') {
        //                 sh "mvn sonar:sonar"
        //             }
        //         }
        //     }   
        // }

        // stage("SonarQube Quality Gates"){
        //     steps{
        //         script {
        //             waitForQualityGate abortPipeline: false, credentialsId: 'sonar-token'
        //         }
        //     }   
        // }

        //  stage("Build & Push Docker Image") {
        //     steps {
        //         script {
        //             docker.withRegistry('',DOCKER_PASS) {
        //                 docker_image = docker.build "${IMAGE_NAME}"
        //             }

        //             docker.withRegistry('',DOCKER_PASS) {
        //                 docker_image.push("${IMAGE_TAG}")
        //                 docker_image.push('latest')
        //             }
        //         }
        //     }

        // }
    }
}