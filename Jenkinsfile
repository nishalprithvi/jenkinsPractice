pipeline{
    agent any

    triggers{
        pollSCM 'H/5 * * * *' //adding build triggers for polling from SCM
    }
    stages{
        stage('Hello'){
            steps {
                echo 'Hello World !! Prithvi here'
            }
        }
        stage('Build'){
            steps {
                echo 'Build stage'
                sh '''
                echo 'Building stuff ....'
                '''
            }
        }
        stage('Test'){
            steps {
                echo 'Test stage'
                sh '''
                echo 'Testing stuff ....'
                python3 main.py
                '''
            }
        }
        stage('Deliver'){
            steps {
                echo 'Deliver stage'
                sh '''
                echo 'Delivering stuff ....'
                '''
            }
        }
        stage('Build docker image'){
            steps {
                script {
                    sh 'docker build -t prithvi-python -f Dockerfile.dockerfile .'
                }
            }
        }
    }
}