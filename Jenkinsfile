pipeline {
  agent any
  stages {
    stage('Lint HTML') {
      sh 'tidy -q -e *.html'
    }
    stage('UploadtoAWS') {
      steps {
        withAWS(region:'us-east-1', credentials:'aws-static') {
          s3Upload(file:'index.html', bucket:'smiddleycicd2', path:'https://smiddleycicd2.s3.amazonaws.com/index.html')
        }
       }
     }
  }
}
