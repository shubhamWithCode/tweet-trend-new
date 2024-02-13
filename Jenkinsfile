pipeline {
    agent {
        node {
            label 'maven'
        }
    }

    stages {
        stage('clone-src-code') {
            steps {
                git branch: 'shubham', credentialsId: 'git-cred', url: 'https://github.com/shubhamWithCode/tweet-trend-new.git'
            }
        }
    }
}
