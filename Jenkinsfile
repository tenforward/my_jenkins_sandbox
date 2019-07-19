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
	stage('stage1') {
	    steps {
	        sh "./stage1.sh"
	    }
	}
    }
}