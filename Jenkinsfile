pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID = 'AWS_ACCESS_KEY_ID'
        AWS_SECRET_ACCESS_KEY = 'AWS_SECRET_ACCESS_KEY'
    }
    stages {
        stage('Submit Stack') {
            steps {
                sh "aws cloudformation create-stack --stack-name s3bucket --template-body file://s3cft.json --region 'us-east-2'"
            }
        }
    }
}
