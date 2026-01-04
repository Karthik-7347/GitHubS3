pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/Karthik-7347/GitHubS3.git'
      }
    }
    stage('Upload to S3') {
      steps {
        withAWS(credentials: 'github-token', region: 'us-east-1') {
          s3Upload(bucket: 'githubs32026', includePathPattern: '**/*')
        }
      }
    }
  }
  triggers {
    pollSCM('')
  }
}
