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
                sh "mvn -Dmaven.repo.local=${WORKSPACE}/develop/m2/repository -f ${WORKSPACE}/pom.xml -U clean install -DskipTests"
            }
        }

        stage('Compile Model') {
            steps {
                sh "pwd"
                sh "mvn -Dmaven.repo.local=${WORKSPACE}/develop/m2/repository -f ${WORKSPACE}/model/pom.xml -U clean install -DskipTests"
            }
        }

        stage('Compile KJAR') {
            steps {
                sh "pwd"
                sh "mvn -Dmaven.repo.local=${WORKSPACE}/develop/m2/repository -f ${WORKSPACE}/kjar/pom.xml -U clean install -DskipTests"
            }
        }

        stage('deploy') {
            steps {
                echo 'Finally Deploying the Build/Project :)'
            }
        }
    }
}