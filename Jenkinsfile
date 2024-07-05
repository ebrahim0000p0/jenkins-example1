pipeline {
    agent any
 /*parameters {
        string(name: 'username', defaultValue: '', description: 'enter user name')
        booleanParam(name: 'isrunning', defaultValue: true, description: 'is docker running')


    }*/

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
		//echo "hello $username"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
		echo "Test auto4"

            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
