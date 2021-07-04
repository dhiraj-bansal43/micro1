pipeline{
    agent {label 'linux'}
    stages{
        stage('Hello'){
            steps{
                echo 'hello from jenkinsfile'
            }
        }
        stage('cat README'){
            when {
                branch "fix-*"
            }
            steps{
                sh 'cat README.md'
            }
        }
        stage('This is for PR'){
            when{
                branch "PR*"
            }
            steps{
                sh 'echo "This is for PR branch"'
            }
        }
    }
}