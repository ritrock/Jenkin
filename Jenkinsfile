pipeline {
    agent {
        kubernetes {
            label 'build-${UUID.randomUUID().toString()}'
            defaultContainer 'jnlp'
            yaml """
            apiVersion: v1
            kind: Pod
            spec:
              containers:
              - name: python
                image: python:3.8
                command: ['cat'] // Keeps the container running
                tty: true
            """
        }
    }

    stages {
        stage('Run Python Script') {
            steps {
                container('python') {
                    script {
                        // Verify Python installation
                        sh 'python --version'

                        // You can run additional Python commands or scripts here
                        sh 'echo "print(\"Hello, World!\")" > hello.py'
                        sh 'python hello.py'
                    }
                }
            }
        }
    }
}
