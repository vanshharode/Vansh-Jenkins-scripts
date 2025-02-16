pipeline {
    agent any
    
    environment {  
        MY_PASSION = 'cloud'
        MY_USER_NAME = 'Vansh'
    }
    
    parameters {
        string(
            name: 'developer_name',
            defaultValue: 'Vansh',
            description: 'Name of the person running the build'
        )
        choice(
            name: 'choice',
            choices: ['dev', 'test', 'uat', 'prod'],
            description: 'Selected environment'
        )
    }
    
    stages {
        stage('demo') {
            steps {
                echo 'hello world'
            }
        }
        stage('Defining Parameter') {
            steps {
                echo "The string parameter is: ${params.developer_name}"
                echo "The selected environment is: ${params.choice}"
            }
        }
        stage('Env Variables') {
            steps {
                echo "My name is ${MY_USER_NAME} and my passion is ${MY_PASSION}"
            }
        }
    }

    post {
        always {
            echo 'Cleaning up the workspace...'
            cleanWs()  
            echo 'Cleaned workspace'
        }
    }
}
