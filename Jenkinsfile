def ret = ""
def ret2 = ""
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
                    ret = sh(script: "./step1.sh", returnStdout: true)
                    echo "$ret"
                }
            }
        }
        stage('step2') {
            steps {
                script {
                    ret2 = sh(script: "./step2.sh ${ret}", returnStdout: true)
                    echo "$ret2"
                }
            }
        }
        stage('job1') {
            steps {
                build "job1"
            }
        }
    }
}