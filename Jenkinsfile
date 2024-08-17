pipeline {
    agent any
    stages {
        stage('Clean') {
            steps {
                deleteDir()
            }
        }
        stage("Clone Repo") {
            steps {
                sh "git clone https://github.com/rwmuteki/simple-node-js-react-npm-app.git"
            }
        }
        stage('Build') { 
            steps {
                dir("simple-node-js-react-npm-app") {
                    sh "npm install"
                }
            }
        }
        stage('Test') {
            steps {
                dir("simple-node-js-react-npm-app") {
                    sh './jenkins/scripts/test.sh'
                }
            }
        }
    }
}