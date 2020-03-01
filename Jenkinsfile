
pipeline {
    agent any
    stages {
        stage('get helm project ') {
            steps {
                sh 'rm -rf  helloworld-chart'
                sh 'mkdir helloworld-chart'
                sh 'cd helloworld-chart'
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


