pipeline {
    agent any
 parameters {
        string(name: 'username', defaultValue: '', description: 'enter user name')
        booleanParam(name: 'isrunning', defaultValue: true, description: 'is docker running')


    }
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
