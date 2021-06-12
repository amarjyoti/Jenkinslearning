pipeline {
    agent any

    stages {
        stage('Clean Workspace') {
            steps {
		echo 'Clean Workspace'
                cleanWs()
            }
        }
        
        stage('Hello Step2') {
            steps {
                echo 'Hello World Step2'
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/amarjyoti/Jenkinslearning.git']]])
                sh '''mkdir test
                    cd test
                    touch file1 file2 file3
		    cd ..
		    zip -r test.zip test'''
            }
        }
		 stage('Build Archive') {
            steps {
		sh '''pwd'''
                archiveArtifacts artifacts: 'test', followSymlinks: false
            }
        }
		
    }
}
