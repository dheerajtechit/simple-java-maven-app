    node () {

	stage ('Barb - Checkout Stage') {
//	 input message: 'Do you Want to Proceed?', submitter: 'admin'
 	    checkout([$class: 'GitSCM',
                branches: [[name: '*/master']], 
                doGenerateSubmoduleConfigurations: false, 
                extensions: [[$class: 'AuthorInChangelog']], 
                submoduleCfg: [], 
                userRemoteConfigs: [[credentialsId: 'f4780c76-dace-43a8-884b-bd1c2cb3bfc8', url: 'https://github.com/ajayshikhare/simple-java-maven-app.git']]]) 

            shortCommit = sh(returnStdout: true, script: "git log -n 1 --pretty=format:'%h'").trim()
	        echo shortCommit
	        
	        Commit_User_Name = sh(returnStdout: true, script: "git --no-pager show -s --pretty=format:'%an'").trim()
	        echo Commit_User_Name
	        
	        Commit_User_Email = sh(returnStdout: true, script: "git --no-pager show -s --pretty=format:'%ae'").trim()
	        echo Commit_User_Email
		
		cleanWs notFailBuild: true
}
    }

    stage ('Barb - Build Stage') {

//      input message: 'Do you Want to Proceed to Compiling the code?', submitter: 'admin' 

    }
