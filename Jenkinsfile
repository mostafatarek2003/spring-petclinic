pipeline {
    agent any
    tools {
        maven 'mvn399'
    }
    parameters { string(name: 'mvn_command_choice', choices: ['package', 'clean', 'test' , 'install'], description: 'choose something from choices list ') }.
    
    stages {
        /*
        stage('Source') {
            steps {
                script {
                    git branch: 'main', poll: false, url: 'git@github.com:mostafatarek2003/spring-petclinic.git'
                }
            }
        }
        */

        stage('mvn command') {
            steps {
                sh "mvn ${params.mvn_command_choice}"
            }
        }
        stage('Package') {
            when {
        branch "feature/*"
    }
            steps {
                sh "mvn package"
            }
        }
        /*
        stage('Test') {
            steps {
                echo "mvn test is start"
            }
        }
        */
    }
}
