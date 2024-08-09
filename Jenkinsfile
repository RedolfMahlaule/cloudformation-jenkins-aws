pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID     = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
    }
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/RedolfMahlaule/cloudformation-jenkins-aws.git'
            }
        }
        stage('Submit Stack') {
            steps {
                sh "aws cloudformation create-stack --stack-name s3bucket --template-body file://s3cft.json --region 'us-east-2'"
            }
        }
    }
}
