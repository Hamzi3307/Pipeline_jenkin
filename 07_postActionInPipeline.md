pipeline{
    agent any

    environment{
        name='Hamza Khan'
        dob='01-07-2001'
    }

    stages{
        stage('Test'){
            steps{
                sh 'echo $name $dob'
            }
        }
    }
    post{
        always{
            sh ' echo "I will always executed"'
        }
        success{
            sh ' echo "I will get executed if test succeeds"'
        }
        failure{
            sh ' echo "I will get executed if test fails"'
        }
        unstable{
            sh ' echo "I will get executed if test unstable"'
        }
    }
}
