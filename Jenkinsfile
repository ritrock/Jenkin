pipeline {
    agent none
    options {
        disableConcurrentBuilds()
    }

    stages {
        stage('Run Python Script') {
            agent {
                kubernetes {
                    label 'build-test'
                    defaultContainer 'python'
                    yaml """
                    apiVersion: v1
                    kind: Pod
                    spec:
                      containers:
                      - name: python
                        image: python:3.8-slim
                        command: ['cat']
                        tty: true
                    """
                }
            }
            steps {
                container('python') {
                    script {
                        sh 'python --version'
                        sh 'echo "print(\"Hello, World!\")" > hello.py'
                        sh 'python hello.py'
                    }
                }
            }
        }
    }
}
