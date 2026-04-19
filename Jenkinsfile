pipeline {
    agent any

    environment {
        TARGET_HOST = "172.31.6.192"
        APP_DIR = "/home/ec2-user/devops-nginx-app"
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/narayanksgit/devops-nginx-app.git'
            }
        }

        stage('Copy files') {
            steps {
                sshagent(credentials: ['ec2-ssh-key']) {
                    sh '''
                        ssh -o StrictHostKeyChecking=no ec2-user@$TARGET_HOST "mkdir -p $APP_DIR"
                        scp -o StrictHostKeyChecking=no Dockerfile index.html ec2-user@$TARGET_HOST:$APP_DIR/
                    '''
                }
            }
        }

        stage('Build and Deploy') {
            steps {
                sshagent(credentials: ['ec2-ssh-key']) {
                    sh '''
                        ssh -o StrictHostKeyChecking=no ec2-user@$TARGET_HOST '
                            cd /home/ec2-user/devops-nginx-app &&
                            docker stop nginx-container || true &&
                            docker rm nginx-container || true &&
                            docker build -t my-nginx-app . &&
                            docker run -d -p 8080:80 --name nginx-container my-nginx-app
                        '
                    '''
                }
            }
        }
    }
}