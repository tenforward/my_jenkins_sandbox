pipeline {
    agent {
        docker {
            image 'ubuntu'
        }
    }
    stages {
        stage('pull') {
            steps {
                git url: 'git@github.com:tenforward/my_jenkins_sandbox.git',
                    branch: 'master'
            }
        }
        node {
            stage('step1') {
                sh ( script: "./step1.sh", returnStatus: true
            }
        }
    }
}