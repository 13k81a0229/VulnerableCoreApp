pipeline {
    agent any

    tools {
        // Make sure this matches your Jenkins global tool config
        dotnet 'dotnet-sdk-7.0'  
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/13k81a0229/VulnerableCoreApp.git'
            }
        }

        stage('Restore') {
            steps {
                sh 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                sh 'dotnet build --configuration Release'
            }
        }

        stage('Test') {
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }

        // Optional: add publish, sonar scan, or deployment here
    }
}
