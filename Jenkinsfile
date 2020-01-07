pipeline {
    agent any
    stages {
        stage ('Say Hello - Build init') {
            steps {
                
                sh 'echo "Hello World - David Walton"'
                
                sh '''
                  echo "Multi-line works too!"
                  ls -lrtha
                '''
            }
        }
        stage ('Upload to AWS') {
            steps {
                
                withAWS(credentials:'aws-static') {
                    // do something
                    s3Upload(bucket:"project3-jenkins", file:'index.html')
                }
            }
        }        
    }
}
