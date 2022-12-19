pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main', url: 'https://github.com/nkishore555/saleor-dashboard.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t kishorekrrish/saleor-dashboar:test .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push kishorekrrish/saleor-dashboar:test'
            }
        }
    }
}
