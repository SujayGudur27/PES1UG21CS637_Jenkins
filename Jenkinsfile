pipeline {
    agent any 
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                           branches: [[name: '*/main']],
                           userRemoteConfigs: [[url: '[6](https://github.com/SujayGudur27/PES1UG21CS637_Jenkins.git)']]])
            }
        }
        
        stage('Build') {
            steps {
                build 'PES1UG21CS637-1'
                sh 'g++ main/hello.cpp -o output'
            }
        }

        stage('Test') {
            steps { 
                sh './output'
            }
        }

        stage('Deploy') { 
            steps { 
                echo 'deploy' 
            } 
        } 

    post { 
        failure { 
            error "Pipeline failed"
         }  
     }  
}
