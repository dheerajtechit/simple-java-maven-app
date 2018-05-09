pipeline {
    agent any
    stages {
        stage('Preview') {
            input {
                message "Continue?"
            }
            steps {
                echo "Preview"
            }
        }
        stage('Testing') {
            failFast true
            parallel {
                stage('QA') {
                    input {
                        id 'testing-qa'
                        message "Continue?"
                    }
                    steps {
                        echo "Testing: QA"
                    }
                }
                stage('Acceptance') {
                    input {
                        id 'testing-acceptance'
                        message "Continue?"
                    }
                    steps {
                        echo "Testing: Acceptance"
                    }
                }
            }
        }
        stage('Compliance') {
            input {
                message "Continue?"
            }
            steps {
                echo "Compliance"
            }
        }
        stage('Staging') {
            input {
                message "Continue?"
            }
            steps {
                echo "Staging"
            }
        }
        stage('Release') {
            input {
                message "Continue?"
            }
            steps {
                echo "Release"
            }
        }
    }
}
