   node () {

	stage ('Barb - Checkout Stage') {
//	 input message: 'Do you Want to Proceed?', submitter: 'admin'
    checkout poll: false, 
    scm: [$class: 'GitSCM', 
    branches: [[name: '*/master']], 
    doGenerateSubmoduleConfigurations: false, 
    extensions: [[$class: 'AuthorInChangelog'], 
    [$class: 'UserIdentity', email: 'GIT_EMAIL=$(git --no-pager show -s --format=\'%ae\' $GIT_COMMIT)', 
    name: 'GIT_NAME=$(git --no-pager show -s --format=\'%an\' $GIT_COMMIT)']], 
    submoduleCfg: [], 
    userRemoteConfigs: [[credentialsId: 'f4780c76-dace-43a8-884b-bd1c2cb3bfc8', 
    url: 'https://github.com/ajayshikhare/simple-java-maven-app.git']]]
}

  stage('Decide') {
        if (env.BRANCH_NAME != 'master') {
            echo 'This build is only meant for Master Branch'
	echo " The PR is ${env.CHANGE_TARGET} or env.CHANGE_ID  or ${env.CHANGE_ID}"
//            sh 'exit 1'
        } else {
            echo 'Building the Master Branch'
		echo " The PR is NOT ${env.CHANGE_TARGET} or env.CHANGE_ID  or ${env.CHANGE_ID}"
//		echo 'Trying MultiBranch Pluigin'
//		sh 'env | sort'
//		sh 'printenv'
        }
    }

    stage ('Barb - Build Stage') {
       input message: 'Do you Want to Proceed to Compiling the code?', submitter: 'admin'
           	}

//	    stage('Branch_Check') {
//	echo "Builing the PR ${env.CHANGE_TARGET}" // One or more steps need to be included within the steps block.
//		    if (env.CHANGE_TARGET()) { 
//		        echo 'This is a pull request' 
//		    } else {
//		    input message: 'Do you Want to Proceed to Compiling the code?', submitter: 'admin'
 //               	echo 'This is NOT a pull request' 
//		    }
	    }
