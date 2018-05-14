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

  stage('Sanity Check') {
	  echo "branch is env.BRANCH_NAME or ${env.BRANCH_NAME} or ${BRANCH_NAME}"
	  echo "If its a Pull Request ${env.CI_PULL_REQUEST} or {CI_PULL_REQUEST} or ${env.CHANGE_ID} or ${CHANGE_ID}"
        	if (env.BRANCH_NAME == 'master' && env.CHANGE_ID == 'true') {
//            	echo 'This build should only be run for the Master Branch and Build can only be run with Pull Request!.'
//	  if {
//            echo 'Building the Master Branch'
//	     echo ' Checking if its a Pull Request.'
//	    if (env.CI_PULL_REQUEST == true)
//	     echo 'Building this Pull Request $GIT_COMMIT from $GIT_NAME'
		
	} else {
            	echo 'This is not a Pull Request Build, Please do not directly commit in master branch, Use Pull Request instead.'
		sh 'exit 1'
        }
    }
		

    stage ('Barb - Build Stage') {
        input message: 'Do you Want to Proceed to Compiling the code?', submitter: 'admin'
        
    }
    }
