pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh ' echo "This is Build Step" '
                sh '''
                echo "By the way e can add more steps too"
                ls -lah
                '''
            }
        }
    }
}
