def ret = ""
def ret2 = ""
def TAKO = ""
def IKA = ""
def HOGE = ""
pipeline {
    agent {
        docker {
            image 'ubuntu'
        }
    }
    stages {
        stage('pull') {
            steps {
                git url: 'https://github.com/tenforward/my_jenkins_sandbox.git',
                    branch: 'master'
            }
        }
        stage('read_env') {
            steps {
                script {
                    TAKO = sh(script: """
		    #!/bin/bash
		    cat ./parameter
		    . ./parameter
		    echo $TAKO
		    """, returnStdout: true)
                }

            }
        }
        stage('echo_env') {
            steps {
              sh "echo $TAKO"
              sh "echo $IKA"
              sh "echo $HOGE"
            }
        }
        stage('step1') {
            steps {
                script {
                    ret = sh(script: "./step1.sh ${VAL}", returnStdout: true)
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
                build(job: "job1", parameters: [string(name: "PARAM", value: "${ret2}")])
            }
        }
    }
}