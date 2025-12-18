pipeline {
    agent any

    environment {
        LIBRARY_REPO='https://github.com/altyapistaj/demo-library.git'
    }

    stages {
        stage('Checkout demo-library') {
            steps {
                echo 'Cloning demo-library repository'
                sh 'rm -rf demo-library && git clone $LIBRARY_REPO demo-library'
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
