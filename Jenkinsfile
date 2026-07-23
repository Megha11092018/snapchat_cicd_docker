pipeline {
    agent any

    tools {
        maven 'maven'
    }

    stages {

        stage('Build') {
            steps {
                echo "Building the project..."
                sh 'mvn clean package'
            }
        }

        stage('Docker Build the Image') {
            steps {
                echo "Building the Docker image..."
                sh 'docker build -t snapchat-cicd-docker .'
            }
        }

        stage('Docker Login to DockerHub') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-cred-id',
                    usernameVariable: 'USER',
                    passwordVariable: 'PASS'
                )]) {
                    sh '''
                        echo "$PASS" | docker login -u "$USER" --password-stdin
                    '''
                }
            }
        }

        stage('Docker Tag the Image') {
            steps {
                echo "Tagging the Docker image..."
                sh 'docker tag snapchat-cicd-docker meghabb11/snapchat-cicd-docker:latest'
            }
        }

        stage('Docker Push the Image') {
            steps {
                echo "Pushing the Docker image to DockerHub..."
                sh 'docker push meghabb11/snapchat-cicd-docker:latest'
            }
        }

        stage('Docker container run') {
            steps {
                script {

                    echo "Checking if container exists..."

                    def containerExists = sh(
                        script: "docker ps -a --format '{{.Names}}' | grep -w snapchat-container || true",
                        returnStdout: true
                    ).trim()

                    if (containerExists) {

                        sh '''
                            docker stop snapchat-container || true
                            docker rm snapchat-container || true
                        '''
                    }

                    sh '''
                        docker run -d \
                        -p 8084:8080 \
                        --name snapchat-container \
                        meghabb11/snapchat-cicd-docker:latest
                    '''
                }
            }
        }

        stage('Docker Logout from DockerHub') {
            steps {
                sh 'docker logout'
            }
        }

        stage('Cleanup Local Docker Images') {
            steps {
                sh '''
                    docker rmi meghabb11/snapchat-cicd-docker:latest || true
                    docker rmi snapchat-cicd-docker || true
                '''
            }
        }

        stage('Done') {
            steps {
                echo "Pipeline execution completed successfully."
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution finished.'
        }

        success {
            echo 'Pipeline completed successfully.'
        }

        failure {
            echo 'Pipeline failed.'
        }
    }
}