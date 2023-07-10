pipeline{
    agent any

    environment{
        name='Hamza Khan'
        dob='01-07-2001'
    }

    stages{
        stage('Compile Stage'){
            steps{
                withMaven(maven:'maven'){
                    sh 'mvn clean compile'
                }
            }
        }
    stage('Test Stage'){
            steps{
                withMaven(maven:'maven'){
                    sh 'mvn test'
                }
            }
        }
    stage('Deployment Stage'){
            steps{ 
                withMaven(maven:'maven'){
                    sh 'mvn deploy'
                }
            }
        }
    }
    post{
        always{
            sh ' echo "I will always executed :D"'
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
