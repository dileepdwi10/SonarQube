pipeline {
   agent any

  //environment {
     // You must set the following environment variables
     // ORGANIZATION_NAME
     // YOUR_DOCKERHUB_USERNAME (it doesn't matter if you don't have one)
     
   //SERVICE_NAME = "fleetman-webapp"
   //REPOSITORY_TAG="${YOUR_DOCKERHUB_USERNAME}/${ORGANIZATION_NAME}-${SERVICE_NAME}:${BUILD_ID}"
  //}

   stages {
      stage('Preparation') {
         steps {
            cleanWs()
            git credentialsId: 'GitHub', url: "https://github.com/dileepdwi10/SonarQube.git"
         }
      }

      stage('Deploy to Cluster') {
          steps {
            sh 'chmod 777 ${WORKSPACE}/deploy.yml'
            sh 'kubectl apply -f ${WORKSPACE}/deploy.yml'
          }
      }
   }
}
