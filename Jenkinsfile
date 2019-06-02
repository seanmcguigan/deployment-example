pipeline {
    agent {label 'slaveOne'}
    
    environment {
        MY_FOO = "foo"
        ORG = "seanmcguigan"
        PROJECT = "webapp"
        HASH = sh(script: 'git rev-parse --short HEAD', returnStdout: true).trim()
    }

    stages {
        stage('Build') {
            steps {
                
                sh """
                echo 'Building...................'
                echo "On branch $env.BRANCH_NAME"
                echo "With build number $env.BUILD_NUMBER"
                echo "With build id $env.BUILD_ID"
                echo "With node name $env.NODE_NAME"
                echo "With git hash $env.HASH"
                docker version
                """
            }
        }
        stage('Test') {
            steps {
              echo 'Testing....'
            }
        }
        stage('Deploy') {
            steps {
              echo 'Deploying....'
            }
        }
    }
 }

