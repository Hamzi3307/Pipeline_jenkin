pipeline{
    agent any

    stages{
        stage('Build'){
            steps{
                retry(3){
                    sh ' Retry me 3 times'
                }
            }
        }
    }
}
