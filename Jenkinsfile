pipline {
    agent any
    stages("Restore project dependencies") {
        stage {
            bat 'dotnet restore'
        }
        stage("Build the project") {
            bat 'dotnet build --no-restore'
        }
        stage("Run tests") {
            bat 'dotnet test --no-build --verbosity normal'
        }
    }
}
