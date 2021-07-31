pipeline{
    agent any
    tools{
        jdk 'java'
        maven 'maven'
        dockerTool 'myDocker'
    }
    stages{
        stage('checkout'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/nns15899/MyEcsConstruct.git']]])

            }

        }
        stage('Installing aws cli on Docker'){
            steps{
                sh 'npm install -g aws-cdk'
                echo 'now installing cdk'


            }
        }
    }
}