pipeline {
    agent any
    stages {
        stage('jdkVersion') {
            steps {
                sh 'java -version'
            }
        }

        stage('Compile Code-MAIN') {
            steps {
                sh "pwd"
                sh "mvn -Dmaven.repo.local=${WORKSPACE}/develop/m2/repository -U clean install"
            }
        }

        stage('build') {
            steps {
                echo 'Build Project...!!'
            }
        }

        stage('test') {
            steps {
                echo 'Running TestCases within Project.'
            }
        }

        stage('deploy') {
            steps {
                echo 'Finally Deploying the Build/Project :)'
            }
        }
    }
}