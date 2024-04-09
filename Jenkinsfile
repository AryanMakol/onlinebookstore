pipeline {  
    agent any  
    
        stages {  
       	    stage('Checkout') {
                                                                steps {
                                                                                                                                            sh 'echo "Checkout stage passed"'
                                                                                                                                            git branch: 'master', url: 'https://github.com/AryanMakol/onlinebookstore.git'
                                                                }
            }
            stage('Build and Test') {
            steps {
                sh 'ls -ltr'
                echo 'Building the project...'
                sh 'mvn clean package'
            }
        }
            stage('deploy'){
                 steps {
                                              echo "deploy stage"
                                               deploy adapters: [tomcat9 (
                                                                                        credentialsId: 'Tomcat_deploy',
                                                                                         path: '',
                                                                                          url: 'http://13.90.134.205:8088/'
                                                                                         )],
                                                                                         contextPath: 'test',
                                                                                          onFailure: 'false',
                                                                                             war: '**/*.war'
                 }
       
        }
}
}
