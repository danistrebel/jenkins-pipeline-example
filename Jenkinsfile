pipeline {
    agent any
    parameters {
        string(defaultValue: 'master', description: 'branch', name: 'GIT_BRANCH')
    }
    stages {
        stage('Example Build') {
            steps {
                echo 'Hello World'
                echo "Branch: ${params.GIT_BRANCH}"
            }
        }
        stage('Example Deploy') {
            when {
                expression { params.GIT_BRANCH ==~ /(production|staging)/ }
            }
            steps {
                echo 'Deploying'
            }
        }
    }
}