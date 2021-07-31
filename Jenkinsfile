pipeline{
agent {
    label "ec2-general-worker-node"
}
    tools{
        jdk 'java'
        maven 'maven'
        dockerTool 'myDocker'
        node 'myNode'
    }
    stages{
        stage('checkout'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/nns15899/MyEcsConstruct.git']]])

            }

        }
        stage('Installing aws cli on Docker'){
            steps{
                sh 'apt-get install npm'
                sh 'npm install -g aws-cdk'
                echo 'now installing cdk'


            }
        }
    }
}