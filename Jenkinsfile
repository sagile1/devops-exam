
pipeline {
    options {
        ansiColor('xterm')
        timestamps()
    }
    stages {
        stage('github init') {
            steps {
                 checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                        userRemoteConfigs: [[url: 'https://github.com/sagile1/devops-exam.git']]])
            }
        }
        stage('Deploy helloworld') {
            steps {
                    ansiblePlaybook(
                    playbook: 'helloworld.yml')
            }
        }
    }
}
