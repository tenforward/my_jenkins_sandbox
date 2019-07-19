pipeline {
    agent {
        image "ubuntu"
    }
    stages {
    	stage('pull') {
	    steps {
	        git url: "git@github.com:tenforward/my_jenkins_sandbox.git",
		    branch: "master"
	    }
	}
        stage('stage1') {
	    steps {
	        def stage1 = sh script: "./stage1.sh", returnStdout: true
	    }
	stage('stage2') {
	    steps {
	        sh script: "./stage2.sh ${stage1}", returnStdout: true
	    }
	}
    }
}