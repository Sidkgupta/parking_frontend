pipeline {
    agent any
        stages{
            stage('Git Checkout'){
                steps{
                    git 'https://github.com/Sidkgupta/parking_frontend.git'
                }
            }
            stage('Build') {
                steps{
                    sh 'npm install'
                    sh 'npm run build'
                    sh 'npm audit fix'
                }
            }
            stage('Deploy'){
                steps{
                    sh 'cp -r $WORKSPACE/build /apache-tomcat-9.0.31/webapps'
                    sh 'curl -u admin:admin http://13.232.229.93:8080/manager/reload?path=/build'
                }
            }
            }
        }
