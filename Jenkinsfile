pipeline {
    agent any

    environment {
        AWS_REGION = 'us-east-1'
        AWS_PROFILE = "Ali's AWS"
        EC2_INSTANCE_ID = 'i-041a774d7ba18abfe'
        S3_BUCKET = 'alikabucket'
    }

    stages {
        stage('Print Information') {
            steps {
                script {
                    echo "AWS Region: ${AWS_REGION}"
                    echo "AWS Profile: ${AWS_PROFILE}"
                    echo "EC2 Instance ID: ${EC2_INSTANCE_ID}"

                    // Use AWS CLI to list S3 buckets
                    def s3Buckets = sh(script: "aws s3 ls s3://${S3_BUCKET} --region ${AWS_REGION} --profile '${AWS_PROFILE}' --output json", returnStdout: true).trim()
                    echo "S3 Buckets: ${s3Buckets}"
                }
            }
        }

        // Add more stages as needed
    }
}

