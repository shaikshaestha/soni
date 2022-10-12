pipeline {
    agent any 
    stages {
        stage('git clone') { 
            steps {
                sh'''
                pwd
                rm -rf *
                git clone https://github.com/shaikshaestha/soni.git"
                '''
            }
        }
        stage('clean') { 
            steps {
                sh'''
                cd soni
                mvn clean
                '''
            }
        }
        stage('compile') { 
            steps {
                sh'''
                cd soni
                mvn compile
                '''
            }
        }
        stage('test') { 
            steps {
                sh'''
                cd soni
                mvn test
                '''
            }
        }
        stage('sonarqube test') { 
            steps {
                sh'''
                cd soni
                mvn sonar:sonar
                '''
            }
        }
    }
}
