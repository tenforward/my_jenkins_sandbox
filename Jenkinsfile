def ret = 0
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
        stage('step1') {
            steps {
                script {
                    ret = sh(script: "./step1.sh", returnStatus: true)
                    echo "$ret"
                }

            }
        }
    }
}