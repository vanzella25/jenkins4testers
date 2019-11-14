pipeline {
    agent {
        docker {
            image "ruby:alpine"
        }
    }
    stages {
        stage("Build") {
            steps {
                sh "chmod +x build/alpine.sh"
                sh "./build/alpine.sh"
                sh "bundler install"
            }
        }
        stage("Tests") {
            steps {
                sh "bundler exec cucumber -p ci'"
            }
        }
    }
}