pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'accelerate-stevenckwong_at_Github', url: 'https://github.com/accelerate-stevenckwong-org/MeOwnBank/']]])
            }
        }
        stage('CI - Package') {
            steps {
                sh 'sleep 1m'
                echo 'Compile, Build and Package'
            }
        }
        stage('CI - Deploy') {
            steps {
                sh 'sleep 30s'
                echo 'Deploy Package to QA App Server'
            }
        }
        stage('CI - Test') {
            steps {
                sh 'sleep 90s'
                echo 'Run some automated test'
            }

        }
    }
    post {
        always {
            sh 'sleep 10s'
        }
    }

}
