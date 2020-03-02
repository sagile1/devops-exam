
pipeline {
    agent any
    stages {
        stage ('echo') {
        sh 'pwd'
        }
        stage('github init') {
            steps {
                 checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                        userRemoteConfigs: [[url: 'https://github.com/sagile1/devops-exam.git']]])
            }
        }
        stage('get helm project ') {
            steps {
                sh 'rm -rf kubernetes-helm-hello-world'
                sh 'git clone https://github.com/pablorsk/kubernetes-helm-hello-world.git'
            }
        }
        stage('Deploy helloworld') {
            steps {
                    ansiblePlaybook(playbook: 'helloworld.yml')
            }
        }
    }
}


