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
                    sh 'cp -r /var/workspace $WORKSPACE/build'
                    sh 'curl -u admin:admin http://13.234.38.1:8080/manager/html/build'
                }
            }
            }
        }
