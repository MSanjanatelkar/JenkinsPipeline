@Library('pipeline-library-demo')_

pipeline {
    agent any
      tools {
       maven 'maven-3.5'
   }
  
   stages{
    stage('connecting to library'){ 
        steps{
            sayHello ''
        }
    }   
    stage('dev'){ 
        steps{
            git 'https://github.com/MSanjanatelkar/spring-app.git'
        }
    }
    stage ('qa'){
        steps{
            sh 'mvn clean install -DskipTests=true'
        }
    }
    stage('preprod') {
      steps {
        parallel(one: {
                  echo "I'm on the first branch!"
                 },
                 two: {
                   echo "I'm on the second branch!"
                 },
                 three: {
                   echo "I'm on the third branch!"
                 })
      }
    }
    stage('prod') {
        steps {
          echo "Deploying"   
        }
    }
  }
} 
   

        
