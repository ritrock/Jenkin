pipeline {
    agent {
        kubernetes {
            label 'build-${UUID.randomUUID().toString()}'
            defaultContainer 'pyhton'
            yaml """
            apiVersion: v1
            kind: Pod
            spec:
              containers:
              - name: python
                image: python:3.8
                command: ['cat']
                tty: true
            """
        }
    }

    stages {
        stage('Run Python Script') {
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
