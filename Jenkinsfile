pipeline {
    agent any 
    stages {
        stage('git clone') { 
            steps {
                sh'''
                pwd
                rm -rf *
                git clone "https://github.com/banawathbalajinaik/google.com.git"
                '''
            }
        }
        stage('clean') { 
            steps {
                sh'''
                cd google.com
                mvn clean
                '''
            }
        }
        stage('compile') { 
            steps {
                sh'''
                cd google.com
                mvn compile
                '''
            }
        }
        stage('test') { 
            steps {
                sh'''
                cd google.com
                mvn test
                '''
            }
        }
        stage('sonarqube test') { 
            steps {
                sh'''
                cd google.com
                mvn sonar:sonar
                '''
            }
        }
    }
}
