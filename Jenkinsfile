pipeline {
    agent any
    stages {
      stage('Upload to AWS') {
        steps {
		  withAWS(region:'us-east-2',credentials:'aws-static')
		  s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'jenkins-pipelines-demo')
          sh 'echo "Hello World"'
		  sh '''
			echo "Multiline shell works too"
			ls -lah
		 '''
        }
      }
    }
}