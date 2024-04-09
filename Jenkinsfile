pipeline {  
    agent any  
        stages {  
       	   stage('Checkout') {
                                                                steps {
                                                                                                                                            sh 'echo "Checkout stage passed"'
                                                                                                                                            git branch: 'dev', url: 'https://github.com/AryanMakol/onlinebookstore.git'
                                                                }
            }
            stage('Build and Test') {
            steps {
                sh 'ls -ltr'
                echo 'Building the project...'
                sh 'mvn clean package'
            }
        }
            stage('install'){
                steps{
                 sh 'mvn install'
        }
            }
}
