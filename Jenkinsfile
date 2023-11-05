pipeline {
    agent any

  triggers {
        cron('* * * * *')
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
