pipeline {
    agent any 
    stages {
        stage('git clone') { 
            steps {
                sh'''
                pwd
                rm -rf *
                git clone "https://github.com/banawathbalajinaik/mavenproject_6.git"
                '''
            }
        }
        stage('clean') {
            steps {
                sh'''
                cd mavenproject_6
                mvn clean
                '''
            }
        }
        stage('compile') { 
            steps {
                sh'''
                cd mavenproject_6
                mvn compile
                '''
            }
        }
        stage('test') { 
            steps {
                sh'''
                cd mavenproject_6
                mvn test
                '''
            }
        }
        stage('sonarqube test') { 
            steps {
                sh'''
                cd mavenproject_6
                mvn sonar:sonar
                '''
            }
        }
    }
}
