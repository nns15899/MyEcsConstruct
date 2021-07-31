pipeline{
    agent any

    tools{
        jdk 'java'
        maven 'maven'
        dockerTool 'myDocker'
        nodejs 'NodeJS'
        
    }
    stages{
        stage('checkout'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/nns15899/MyEcsConstruct.git']]])
            }

        }
        stage('install dependencies') { 
            steps {
                sh 'npm -v'
                echo 'npm installed !'
                echo 'installing cdk'
                sh 'npm install -g aws-cdk'
                sh 'cdk --version'
            }
        }
        stage('checking cdk'){
            steps{
                sh 'cdk --version'
                echo 'everything is working fine'
            }
        }

    }
}