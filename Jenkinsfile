pipeline {
    agent any
    tools{
      maven 'M2_HOME'
    }
     stages{
        stage('sonarqube scan'){
            steps{
                withSonarQubeEnv('sonarserver'){ 
              sh 'mvn verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -Dsonar.projectKey=Abz1996_hola'
             // sh 'mvn sonar:sonar'
            }
            }
        }
     }
     
      stage('clean'){
       steps {
         sh 'mvn clean'
       }
    }
    stage('compile'){
      steps{
        sh 'mvn compile'
      }
    }
    stage('install'){
      steps{
        sh 'mvn install'
        sh 'mvn package'

      }
    }
    
    }

}
