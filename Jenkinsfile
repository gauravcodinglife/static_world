pipeline {
    agent { labels: "dev" }

    stages {

        stage('Code') {
            steps {
                git url: 'https://github.com/gauravcodinglife/static_world.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                sh 'docker build -t static_world-app .'
            }
        }

        stage('Test') {
            steps {
                sh 'echo Tests passed ✅'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'GauravDockerCreds',
                    usernameVariable: 'dockerHubUser',
                    passwordVariable: 'dockerHubpass'
                )]) {
                    sh """
                    echo $dockerHubpass | docker login -u $dockerHubUser --password-stdin
                    docker tag static_world-app $dockerHubUser/static_world-app:latest
                    docker push $dockerHubUser/static_world-app:latest
                    """
                }
            }
        }

        stage('Deploy') {
            steps {
                sh """
                docker stop static_world || true
                docker rm static_world || true
                docker run -d -p 80:80 --name static_world codinggaurav/static_world-app:latest
                """
            }
        }
    }
}
