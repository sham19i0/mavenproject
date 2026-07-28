pipeline {
    agent any

    stages {

        stage('Clone Java Repository') {
            steps {
                dir('java-project') {
                    git 'https://github.com/Sharath-yp25/java.git'
                }
            }
        }

        stage('Clone Maven Repository') {
            steps {
                dir('maven-project') {
                    git 'https://github.com/Sharath-yp25/mavenproject.git'
                }
            }
        }

        stage('Execute Java Project') {
            steps {
                dir('java-project') {
                    bat '''
                        javac Test.java
                        java Test
                    '''
                }
            }
        }

        stage('Generate Maven Package') {
            steps {
                dir('maven-project') {
                    bat 'mvn clean package'
                }
            }
        }

    }
}
