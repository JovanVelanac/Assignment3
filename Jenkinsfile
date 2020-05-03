pipeline {
    agent any

    stages{
        stage('Build image') {
            script {
                app = docker.build("jovanvelanac/assignment3")
            }
        }

        stage('Push image') {
            script{
                docker.withRegistry('https://registry.hub.docker.com', 'docker-credentials') {
                app.push("${env.BUILD_NUMBER}")
                app.push("latest")
                }
            }
        }
    }
}
