pipeline {
    agent any
    tools {
        maven 'mvn399'
    }
    parameters {
        choice(name: 'mvn_command_choice', choices: ['package', 'clean', 'test', 'install'], description: 'Choose an option')
    }

    stages {
        /*
        stage('Source') {
            steps {
                script {
                    git branch: 'main', poll: false, url: 'git@github.com:mostafatarek2003/spring-petclinic.git'
                }
            }
        }
        

        stage('Maven Command') {
            steps {
                sh "mvn ${params.mvn_command_choice}"
            }
        }
        /*

        stage('Package') {
            when {
                expression { env.BRANCH_NAME.startsWith('feature/') }
            }
            steps {
                sh "mvn package"
            }
        }

        */
        stage('deploy') {
            steps {
                script{
                sshPublisher(publishers: [sshPublisherDesc(configName: 'mostafa-server', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'mostafa_script.py')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])            }
        }}
        
    }
}
