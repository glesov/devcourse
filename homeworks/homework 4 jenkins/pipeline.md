pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh "sudo docker build -t glesov1/rs1:$BUILD_NUMBER /home/gena/homework/my_python_app/"
                echo 'Build Image Completed'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                withCredentials( [usernamePassword( credentialsId: 'docker_hub_glesov2', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                    sh "sudo docker push glesov1/rs1:$BUILD_NUMBER"
                    echo 'Push to Docker Hub Completed'
                }
            }
        }
    }
}
