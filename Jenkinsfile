pipeline {
    agent any
    
    parameters {
        string(name: 'PR_NUMBER', defaultValue: '', description: 'Enter the PR number')
    }
    
    stages {
        stage('Checkout PR Branch') {
            steps {
                script {
                    def prNumber = params.PR_NUMBER
                    echo "PR Number: ${prNumber}"
                    
                    // Checkout the PR branch
                    checkout([$class: 'GitSCM', branches: [[name: "refs/pull/${prNumber}/head"]], userRemoteConfigs: [[url: 'https://github.com/sumamohan143/test-pr.git']]])
                }
            }
        }
        
        stage('Build') {
            steps {
                // Your build steps here, using the content from the PR branch
                echo "Your build steps here, using the content from the PR branch"
                echo "Extra Line"
            }
        }
    }
}
