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
                    sh 'cp -r $jenkins_home/build /var/workspace'
                    sh 'curl -u admin:admin http://13.234.38.1:8080/manager/reload?path=/build'
                }
            }
            }
        }
