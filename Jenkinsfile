pipeline {
    agent any
    
    stages {
        stage('Checkout PR Branch') {
            steps {
                script {
                    // Use the CHANGE_ID environment variable to get the PR number
                    def prNumber = env.CHANGE_ID
                    echo "PR Number: ${prNumber}"
                    
                    // Checkout the PR branch
                    checkout([$class: 'GitSCM', branches: [[name: "refs/pull/${prNumber}/merge"]], userRemoteConfigs: [[url: 'https://github.com/sumamohan143/test-pr.git']]])
                }
            }
        }
        
        stage('Build') {
            steps {
                echo " Your build steps here, using the content from the PR branch"
            }
        }
    }
}
