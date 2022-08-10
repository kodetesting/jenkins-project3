pipeline {
    agent any
    stages {
        stage('jdkVersion') {
            steps {
                sh 'java -version'
            }
        }

        stage('JBPMPackageValidation') {
            steps {
                sh "mkdir develop"
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