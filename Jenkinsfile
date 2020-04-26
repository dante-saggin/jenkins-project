pipeline {
	agent any
	stages {
		stage("Lint HTML") {
			steps {
				sh '''
					tidy -q -e *.html
				'''
			}
		}
		stage("Upload to AWS") {
			steps {
				sh '''
					echo "multiline shell works too"
					ls -ltra
				'''
				withAWS(region:'us-west-2',credentials:'aws-static',) {
    				s3Upload(file:'index.html', bucket:'jenkins-dhss-cde', path:'index.html')
				}
			}
		}
	}
}