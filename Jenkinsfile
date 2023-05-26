pipeline {
  agent any
  tools { 
        maven 'Maven_3_5_2'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=methamodewebapp -Dsonar.organization=methamodewebapp -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=c2100e48ae53ff3fa37e7dc8902b5762b3316122'
			}
        } 
     stage('SAST Scan') {
              steps {
		git 'https://github.com/asecurityguru/just-another-vulnerable-java-application.git'
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=methamodewebapp -Dsonar.organization=methamodewebapp -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=c2100e48ae53ff3fa37e7dc8902b5762b3316122'
			}
        }
  }
}
