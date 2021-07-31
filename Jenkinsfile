pipeline{
    agent any
    
    tools{
        jdk 'java'
        maven 'maven'
        dockerTool 'myDocker'
        
    }
    stages{
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
        stage('checkout'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/nns15899/MyEcsConstruct.git']]])
            }

        }
    }
}