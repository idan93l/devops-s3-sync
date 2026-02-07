pipeline {
  agent any

  environment {
    AWS_DEFAULT_REGION = 'us-east-1'
    AWS_ACCESS_KEY_ID     = credentials('AWS_ACCESS_KEY_ID')
    AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
    S3_BUCKET = 's3://idan-jenkins-deploy-us-east-1-2026'
  }

  stages {
    stage('Sync to S3') {
      steps {
        bat '"C:\\Program Files\\Amazon\\AWSCLIV2\\aws.exe" s3 sync . %S3_BUCKET% --delete'
      }
    }
  }
}
