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
}

    stage('Check The Environment') {
            when {
            branch 'dev' 
            }
            steps {
 //               sh './jenkins/scripts/deliver-for-development.sh'
                input message: 'This is the Dev Branch? (Click "Proceed" to continue)'
                sh 'echo "Code Stops Here"'
            }

    stage('Check The Environment') {
            when {
            branch 'master' 
            }
            steps {
 //               sh './jenkins/scripts/deliver-for-development.sh'
                input message: 'This is the Prod Branch? (Click "Proceed" to continue)'
                sh 'echo "Code would be deployeed into PROD env"'
            }
    }

    stage ('Barb - Build Stage') {
        input message: 'Do you Want to Proceed to Compiling the code?', submitter: 'admin'
        
    }
    }
