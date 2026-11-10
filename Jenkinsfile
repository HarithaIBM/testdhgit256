rbject utils = null

pipeline {
    agent {
        node {
            label 'BCPBOT_STATUS_CHECK'
        }
    }
    options {
        skipDefaultCheckout true
    }
    environment {
        // Define environment variables here as needed
        SOME_VARIABLE="test" //Jenkins requires you to have some var here
    }
    stages {
        stage ('Status Check') {
            steps {
                script {
                    utils = new Utils()
                    utils.generic_repo_status_check()
                }
            }
        }
    }
    post {
        cleanup {
            echo "Cleaning up workspace (deletes all files)"
            cleanWs()
        }
    }
}
