pipeline {
    agent any

    triggers {
    pollSCM('H * * * *')
    }

    stages {
        stage ('Copy Chef configuration files to directory') {
            steps {
                sh 'cp -R /chef .chef'
            }
        }
        stage ('Upload new role') {
            steps {
                sh 'ls | grep .json | knife upload .'
            }
        }
        stage ('Remove Chef configuration file') {
            steps {
                sh 'rm -R .chef'
            }
        }
    }
}