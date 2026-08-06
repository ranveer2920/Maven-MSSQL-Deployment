pipeline {

    agent any

    stages {

        stage('Build Docker Image') {
    steps {
        sh 'docker build -t ranveer0318/maven-mssql-app:1.0 .'
    }
}

stage('Run Docker Container') {
    steps {
        sh '''
        docker rm -f maven-app || true
        docker run -d \
            -p 8080:8080 \
            --name maven-app \
            ranveer0318/maven-mssql-app:1.0
        '''
    }
}
