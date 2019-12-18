pipeline{
    agent any
    tools{
        maven "m3"
        jdk "jdk8"
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
        stage('test'){
            steps{
                sh "mvn test"
            }
        }
    }
}
