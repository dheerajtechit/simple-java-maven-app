    node () {

	stage ('Barb - Checkout Stage') {
	 input message: 'Do you Want to Proceed?', submitter: 'admin'
    checkout poll: false, 
    scm: [$class: 'GitSCM', 
    branches: [[name: '*/master']], 
    doGenerateSubmoduleConfigurations: false, 
    extensions: [[$class: 'AuthorInChangelog'], 
    [$class: 'UserIdentity', 
    email: 'GIT_EMAIL=$(git --no-pager show -s --format=\'%ae\' $GIT_COMMIT)', 
    name: 'GIT_NAME=$(git --no-pager show -s --format=\'%an\' $GIT_COMMIT)']], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'f4780c76-dace-43a8-884b-bd1c2cb3bfc8', url: 'https://github.com/ajayshikhare/simple-java-maven-app.git']]]	
}
	    
	    stage('Branch_Check') {
//	echo "Builing the ${env.changeRequest}"// One or more steps need to be included within the steps block.
	input message: 'Do you Want to Proceed to Compiling the code?', submitter: 'admin'
		    
  when {
    changeRequest()
  }
}

    }
