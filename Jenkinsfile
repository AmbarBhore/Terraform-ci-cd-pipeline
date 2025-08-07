pipeline {
     agent any
     stages {
	stage('Deploy to AWS') {
	    steps {
		withAWS(credentials: 'aws-creds', region: 'ap-south-1') {
		    sh 'aws s3 ls'
		    sh 'terraform apply -auto-approve'
		}
	     }
	 }
	 stage('Debug AWS Path') {
            steps {
                sh 'which aws || echo "AWS not found"'
                sh 'echo $PATH'
                sh 'aws --version || echo "AWS CLI not working"'
            }
      	 }
     }
}
