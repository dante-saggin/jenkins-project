pipeline {
	agent any
	stages {
		stage("Upload to AWS") {
			steps {
				sh '''
					echo "multiline shell works too"
					ls -ltra
				'''
				withAWS(region:'eu-west-2',credentials:'aws-static',) {
    				s3Upload(file:'index.html', bucket:'jenkins-dhss-cde', path:'.')
				}
			}
		}
	}
}