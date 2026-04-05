pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main', url: 'https://github.com/aryan249123-rgb/dockerprojectrep.git'
            }
        }

        stage('Verify HTML File') {
            steps {
                bat 'dir'
                bat 'type index.html'
            }
        }

        stage('Success Message') {
            steps {
                echo 'HTML project successfully fetched and verified!'
            }
        }
    }
}
