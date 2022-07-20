pipeline {
    
    agent any
    
stages {
 stage('Checkout') {
    steps {
     git url: 'https://github.com/Kabi16/Core-Helloworld.git', branch: 'master'
     }
  }

stage('Restore'){
   steps{
      bat "dotnet restore --configfile "C:\Project\HelloWorld\.nuget\nuget.config" 
     
    }
 }

stage('Build'){
   steps {
     bat "dotnet build C:\Project\HelloWorld\dotnetHelloWorld.sln /t:Rebuild /v:m /m:2 /p:Configuration=Release /clp:ErrorsOnly /fl /flp:ErrorsOnly;WarningsOnly"
     }
  }
    
stage('Publish'){
     steps{
       bat "dotnet publish dotnet build "C:\Project\HelloWorld\src\dotnetHelloWorld\dotnetHelloWorld.csproj" /p:PublishProfile=Release /p:PackageLocation="C:\Project\HelloWorld\src\dotnetHelloWorld\src\dotnetHelloWorld\bin\Release1\package.zip" /p:DeployOnBuild=true /p:WebPublishMethod=Package /p:PackageAsSingleFile=true /p:platform="Any CPU" /p:configuration="Release" "
     }
  }
 }
}
