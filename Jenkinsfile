pipeline {
    agent any

    stages {
        stage('Hello Step1') {
            steps {
                echo 'Hello World Step1'
            }
        }
        
        stage('Hello Step2') {
            steps {
                echo 'Hello World Step2'
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/amarjyoti/Jenkinslearning.git']]])
                sh '''mkdir test
                    cd test
                    touch file1 file2 file3'''
            }
        }
    }
}
