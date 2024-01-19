pipeline {
    agent any
    tools{
      maven 'M2_HOME'
    }
     stages{
        stage('sonarqube scan'){
            steps{
                withSonarQubeEnv('sonarserver'){ 
              sh 'mvn verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -Dsonar.projectKey=kserge2001_week16-code'
             // sh 'mvn sonar:sonar'
            }
            }
        }
     }
     stages{
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
