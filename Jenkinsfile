pipeline{
    tools{
        jdk 'myjdk8'
        maven 'mymaven'
    }
    
    agent none
    stages {
        stage('Compile'){
            agent any
            steps{
                sh 'mvn compile'
            }
        }
        stage('Test'){
            agent any
            steps{
                sh 'mvn test'
            }
            post{
                always{
                    junit 'gameoflife-web/target/surefire-reports/*.xml'
                    
                }
            }
        }
        stage('Package'){
            agent any
            steps{
                git 'https://github.com/jyoti9112/localrepo1.git'
                sh 'mvn package'
            }
        }
    }
    
    
}
