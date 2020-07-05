pipeline {
    agent any
    stages {
      stage('Upload to AWS') {
        steps {
		  withAWS(region:'us-east-2',credentials:'aws-static'){
		  sh 'echo "Uploading content"'
		  s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'jenkins-pipelines-demo')
          }
        }
      }
    }
}