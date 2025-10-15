pipeline {
    agent {
        docker {
            image 'mcr.microsoft.com/dotnet/sdk:8.0'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    stages {
        stage("Restore project dependencies") {
            steps{
                sh 'dotnet restore'
            }
        }
        stage("Build the project") {
            steps {
                sh 'dotnet build --no-restore'
            }
        }
        stage("Run tests") {
            steps  {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
