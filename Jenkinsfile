pipeline{
    agent any

    tools{
        jdk 'java'
        maven 'maven'
        dockerTool 'myDocker'
        nodejs 'node'
        
    }
    stages{
        stage('checkout'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/nns15899/MyEcsConstruct.git']]])
            }

        }
        stage('install dependencies') { 
            steps {
                sh 'npm install' 
            }
        }

    }
}