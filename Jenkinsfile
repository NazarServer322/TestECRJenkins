pipeline {
    agent {
        label 'ubuntu'
    }
    environment {
     registry = "12345.dkr.ecr.eu-north-1.amazonaws.com/hello-world"
    }
    stages {
        // it's how to find our github without SCM inside jenkins 
        stage('gitchecout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/NazarServer322/TestcECRJenkins.git']]])
            }
            }
            
        stage('Building image') {
            steps{
             sh 'sudo docker build -t 1124124125124.dkr.ecr.eu-north-1.amazonaws.com/hello-world .'
            }
            }
          // Here i'm  find not best practice to login in docker ECR but it's work. First of all need find the key here need write the command:
          //aws ecr get-login-password --region eu-north-1 and then make docker login -u aws -p   ssh key super long (awsID).dkr.ecr.(region).amazonaws.com
 

        stage('docker login') {
            steps{
             sh 'sudo docker login -u AWS -p 412412412412414125125215l1QTkyTDF1234mJ3a1NWY0xUUm5213aEZObklRS1hwWnJaOHhJVnJZYXJyQU15XNyTDVkRjZmK0t52FlkMWNCTmZwZ2dLd21234a0d3dDJ5'
            }
            }
           // In AWS ECR we have to change name our docker image  and give the name our ECR registry for our docker image 
        stage('docker rename for aws') {
            steps{
             sh 'sudo docker tag pythonapp:v1 1234.dkr.ecr.eu-north-1.amazonaws.com/hello-world'
            }
            }
        stage('docker push') {
            steps{
             sh 'sudo docker push 12412.dkr.ecr.eu-north-1.amazonaws.com/hello-world'
            }
            }
        stage('docker run') {
            steps{
             sh 'sudo docker run -d  -p 8096:5000 --restart=always --name awsdocker  124124.dkr.ecr.eu-north-1.amazonaws.com/hello-world'
            }
            }    
            
}
}
