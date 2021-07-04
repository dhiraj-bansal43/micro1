pipeline{
    agent {label 'linux'}
    options{
        buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr:'5', daysToKeepStr: '', numToKeepStr: '5')
        disableConcurrentBuilds()
    }
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