pipeline {

   

    agent any

    stages{

        stage('Build'){

            steps { 

                sh 'mvn clean package'
     
            }

            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts :  '**/target/*.war'

                }

            }

        }

       stage('sonarqube'){
          steps { 

                sh 'mvn verify sonar:sonar'
     
            }
           
        }

    }

}
