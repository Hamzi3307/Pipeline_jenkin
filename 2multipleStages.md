pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "This is Build Step"
            }
        }
        stage('Test') {
            steps {
                echo 'This is Test Step'
            }
        }
        stage('Deploy') {
            steps {
                echo 'This is Deploy Step'
            }
        }
    }
}
