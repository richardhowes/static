pipeline {
  agent any
  stages {
    stage ('Upload to AWS') {
      steps {
        withAWS(region:'us-west-2',credentials:'aws-static')
	s3Upload(bucket:'project3-jenkins',file:'index.html')
      }
    }
  }
}
