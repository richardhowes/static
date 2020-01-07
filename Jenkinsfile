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
        stage ('Lint HTML') {
            steps {
                sh "tidy -q -e index.html"
            }
        }
        stage ('Upload to AWS') {
            steps {
                
                withAWS(credentials:'aws-static') {
                s3Upload(bucket:"project3-jenkins", file:'index.html')
                }
            }
        }
    }
}
