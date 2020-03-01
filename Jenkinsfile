
pipeline {
    agent any
    stages {
        stage('echo') {
            steps {
                sh 'pwd'
                sh 'whoami'
            }
        }
        stage('github init') {
            steps {
                 checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                        userRemoteConfigs: [[url: 'https://github.com/pablorsk/kubernetes-helm-hello-world.git']]])
            }
        }
        stage('Deploy helloworld') {
            steps {
                    ansiblePlaybook(playbook: 'helloworld.yml')
            }
        }
    }
}


