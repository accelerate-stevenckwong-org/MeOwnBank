pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'StevenCKWong_Github', url: 'https://github.com/stevenckwong/Toystore']]])
            }
        }
        stage('CI - Package') {
            steps {
                sleep 1m
                echo 'Compile, Build and Package'
            }
        }
        stage('CI - Deploy') {
            steps {
                sleep 30s
                echo 'Deploy Package to QA App Server'
            }
        }
        stage('CI - Test') {
            steps {
                sleep 90s
                echo 'Run some automated test'
            }

        }
    }
    post {
    }

}
