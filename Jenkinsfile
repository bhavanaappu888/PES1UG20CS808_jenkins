pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'g++ mvn test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'g++ deploy_script.sh'
            }
        }
    }

    post {
        always {
            script {
                if (currentBuild.result == 'FAILURE') {
                    echo 'Pipeline failed'
                }
            }
        }
    }
}
