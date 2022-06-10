pipeline{
    agent any
    // tools {
    //     maven 'sonar-jenkins'
    // }
    environment {
        PATH = "$PATH:/usr/share/maven/bin"
    }
    stages{
       stage('GetCode'){
            steps{
                git 'https://github.com/sonica29/hello-world.git'
            }
         }        
    //   stage('Build'){
    //         steps{
    //             sh 'mvn clean package'
    //         }
    //      }
        stage('SonarQube analysis') {
//    def scannerHome = tool 'SonarScanner 4.0';
        steps{
        withSonarQubeEnv('sonar-jenkins') { 
        // If you have configured more than one global server connection, you can specify its name
//      sh "${scannerHome}/bin/sonar-scanner"
        sh "mvn sonar:sonar"
    }
        }
        }
       
    }
}
