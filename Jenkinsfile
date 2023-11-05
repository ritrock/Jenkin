pipeline {
    agent any

  triggers {
        cron('0,7,14,21,28,35,42,49,56 * * * *')
    }
    stages {
        stage('Build') {
            steps {
             echo "This is Building Stage...."
            }
		}
        stage('Test') {
            steps {
             echo "This is Testing Stage...."
            }
		}
        stage('Deploy') {
            steps {
             echo "This is Deploying Stage...."
            }

		}
	}
    post {
        success {
                    echo "Script Ran successfully"
                }
            }
  }
