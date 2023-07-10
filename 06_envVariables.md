pipeline{
    agent any

    environment{
        name='Hamza Khan'
        dob='01-07-2001'
    }

    stages{
        stage('Build'){
            steps{
                sh 'echo $name $dob'
            }
        }
    }
}
