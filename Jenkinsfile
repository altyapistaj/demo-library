pipeline {
    agent {
        label 'jenkins-agent'
    }

    environment {
        LIBRARY_REPO='https://gitlab.com/altyapistaj-group/demo-library.git'
    }

    stages {
        stage('Checkout demo-library') {
            steps {
                sshagent(credentials: ['gitlab-ssh-key']){
                echo 'Cloning demo-library repository'
                sh 'rm -rf demo-library && git clone $LIBRARY_REPO demo-library'
                }
            }
        }
        stage('Build Jar'){
            steps{
                dir('demo-library'){
                    sh 'mvn clean install'
                }
            }
        }
    }
}
