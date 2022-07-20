pipeline {
    
    agent any
    
stages {
 stage('Checkout') {
    steps {
     git url: 'https://github.com/Kabi16/Project.git', branch: 'master'
     }
  }

stage('Restore packages'){
   steps{
      bat "dotnet restore C:\\Users\\C605978\\source\\repos\\Project\\Project\\Project.csproj"
     }
  }

stage('Clean'){
    steps{
        bat "dotnet clean C:\\Users\\C605978\\source\\repos\\Project\\Project\\Project.csproj"
     }
   }

stage('Build'){
   steps{
      bat "dotnet build C:\\Users\\C605978\\source\\repos\\Project\\Project\\Project.csproj --configuration Release"
    }
 }

stage('Test: Unit Test'){
   steps {
     bat "dotnet test C:\\Users\\C605978\\source\\repos\\Project\\Project\\Project.csproj"
     }
  }
       
 stage('Test: Integration Test'){
    steps {
       bat "dotnet test C:\\Users\\C605978\\source\\repos\\Project\\Project\\Project.csproj"
      }
   }
    
stage('Publish'){
     steps{
       bat "dotnet publish C:\\Users\\C605978\\source\\repos\\Project\\Project\\Project.csproj "
     }
  }
 }
}
