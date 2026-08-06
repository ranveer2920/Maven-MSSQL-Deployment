pipeline {

    agent any

    stages {

        stage('Checkout') {

            steps {

                git branch: 'main',
                    url: 'https://github.com/ranveer2920/Maven-MSSQL-Deployment.git'

            }
        }

        stage('Build Maven') {

            steps {

                sh 'mvn clean package'

            }
        }

    }

}
