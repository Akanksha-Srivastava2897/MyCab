pipeline {
    agent any

    stages {
        stage('Checkout') {
        steps {
            checkout([$class: 'GitSCM', branches: [[name: '*/MC1']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'feaaf2b8-524d-4ead-bdba-65d12938a0ff', url: 'https://github.com/akanksha2897/MyCab.git']]])
            }
        }
        stage('Build') {
            steps {
                echo 'Job has been build'
            }
        }
         stage('Test') {
            steps {
                echo 'Job has been test'
            }
        }
        stage('QA Deploy') {
            steps {
                echo 'Job has been deployed'
            }
        }
         stage('Prod Deploy') {
            steps {
                echo 'Production Deployment done'
            }
        }
    }
}