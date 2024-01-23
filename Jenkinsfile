pipeline {
    agent any
    triggers {
        githubPush()
    }
     stages {
        stage("Build") {
            steps {
                sh "npm install"
                sh "npm run build"
            }
        }
        stage("Deploy") {
            steps {
                sh "sudo rm -rf /var/www/test-jenkins"
                sh "sudo cp -r ${WORKSPACE}/build/ /var/www/test-jenkins/"
            }
        }
    }
}