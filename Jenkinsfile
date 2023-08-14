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
                    
                    // Fetch and checkout the pull request branch
                    sh "git fetch origin pull/${prNumber}/head:pr${prNumber}"
                    sh "git checkout pr${prNumber}"
                }
            }
        }
        
        stage('Build') {
            steps {
                // Your build steps here, using the content from the PR branch
                echo "Your build steps here, using the content from the PR branch"
            }
        }
    }
}
