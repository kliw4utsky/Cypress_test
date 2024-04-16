pipeline {
    agent any

    tools {
        nodejs "Node21"
    }

    environment {
        CHROME_BIN = '/bin/google-chrome'
    }

    stages {
        stage('Dependencies') {
            steps {
                sh 'npm i'
            }
        }
        stage('e2e Tests') {
            steps {
                script {
                    parallel(
                        "Test 1": {
                            sh 'echo 1111 | sudo -S npm run cypress:ci'
                        },
                        "Test 2": {
                            sh 'echo 1111| sudo -S npm run cypress2:ci'
                        }
                    )
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
