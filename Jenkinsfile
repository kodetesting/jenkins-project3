pipeline {
    agent any

    tools {
      maven 'maven'
    }

    stages {
        stage('jdkVersion') {
            steps {
                sh 'java -version'
            }
        }

        stage('Compile MAIN') {
            steps {
                sh "pwd"
                sh "mvn -Dmaven.repo.local=${WORKSPACE}/develop/m2/repository -U clean install"
            }
        }

        stage('Compile SERVICE') {
            steps {
                sh "cd service/"
                sh "pwd"
                sh "mvn -Dmaven.repo.local=${WORKSPACE}/develop/m2/repository -U clean install"
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