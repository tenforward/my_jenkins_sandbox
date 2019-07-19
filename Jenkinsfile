pipeline {
    agent {
        image "ubuntu"
    }
    stages {
        stage('stage1') {
	    steps {
	        def stage1 = sh script: ./stage1.sh, returnStdout: true
	    }
	stage('stage2') {
	    steps {
	        sh script: "./stage2.sh ${stage1}", returnStdout: true
	    }
	}
    }
}