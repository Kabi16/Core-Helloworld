pipeline {
    
    agent any
    
stages {
 stage('Checkout') {
    steps {
     git url: 'https://github.com/Kabi16/Project.git', branch: 'master'
     }
  }

stage('Build'){
   steps{
      bat "call Build.cmd"
    }
 }
    
stage('Publish'){
     steps{
       bat "call Publish.cmd"
     }
  }
 }
}
