pipeline {
    agent any
    tools {
        maven 'maven399'
    }
    stages {
        stage('Source') {
            steps {
                script {
                    git branch: 'main', poll: false, url: 'git@github.com:mostafatarek2003/spring-petclinic.git'
                }
            }
        }
        stage('Package') {
            steps {
                sh "mvn package"
            }
        }
        stage('Test') {
            steps {
                sh "mvn test"
            }
        }
    }
}
