pipeline {
    agent any

    stages {
        stage('AWS STS') {
            steps {
                echo 'AWS STS'
                sh 'aws sts get-caller-identity'
            }
        }
        stage('AWS s3 list') {
            steps {
                echo 'AWS STS'
                sh 'aws s3 ls'
            }
        }
        stage('GIT git clone') {
            steps {
                echo 'Git clone'
                sh 'rm -rf jenkins-website/'
                sh 'git clone https://github.com/rdespitia70/jenkins-website.git'
                sh 'ls -lrt jenkins-website/'
            }
        }
        stage('Upload to s3') {
            steps {
                sh 'aws s3 cp jenkins-website s3://jenkins-bootcamp-rdem --recursive'
            }
        }
    }
}
