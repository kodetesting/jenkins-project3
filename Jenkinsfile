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
                sh "mvn -Dmaven.repo.local=${WORKSPACE}/develop/m2/repository -U clean install -DskipTests"
            }
        }

        stage('Compile KJAR') {
            steps {
                sh "cd ${WORKSPACE}/kjar/"
                sh "pwd"
                sh "mvn -Dmaven.repo.local=${WORKSPACE}/develop/m2/repository -U clean install -DskipTests"
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