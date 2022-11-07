pipeline {
    agent any

    stages {
        stage('AWS VALIDATE!') {
            steps {
                echo 'AWS STS'
                sh 'aws sts get-caller-identity'
            }
        }
        stage('AWS S3 listar') {
            steps {
                sh 'aws s3 ls'
            }
        } 
        stage('Git Clone') {
            steps {
                sh 'rm -rf DesafioJenkins2/'
                sh 'git clone https://github.com/lucaspedernera27/DesafioJenkins2.git'
                sh 'ls -lrt DesafioJenkins2/'
            }
        } 
        stage('Upload to S3') {
            steps {
                sh 'aws s3 cp DesafioJenkins2 s3://bucketjenkinslp --recursive'
            }
        }         
    }
}
