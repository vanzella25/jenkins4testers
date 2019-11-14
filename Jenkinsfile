pipeline {
    agent {
        docker {
            image "ruby"
        }
    }
    stages {
        stage("Build") {
            steps {
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