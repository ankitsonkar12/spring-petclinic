pipeline{
    agent any
    tools{
        maven "m3"
        java "jdk8"
    }
    triggers{
        pollSCM("* * * * *")
    }
    stages{
        stage('checkout'){
            steps{
                checkout scm
            }
        }

        stage('build'){
            steps{
                sh "mvn clean compile"
            }
        }
        stage('test')
        {
            steps{
                 sh "mvn test"

            }
           
        }
        stage('Test Report') {
          steps {
              script {
                junit '**/surefire-reports/*.xml'
              }
          }
        }
        

    }
}