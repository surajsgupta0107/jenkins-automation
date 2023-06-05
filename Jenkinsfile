pipeline {
    agent any
    environment {
        name = "Suraj Gupta"
    }
    parameters {
        string(name: "person", defaultValue: "Suraj Gupta", description: "who are you?")
        booleanParam(name: "is_active", defaultValue: false, description: "if person is active or not?")
        choice(name: "city", choices: ["Mumbai", "Gorakhpur", "Kaashi", "Ayodhya", "Mathura"], description: "")
    }
    stages {
        stage("Ram"){
            steps {
                echo "Jai Shri Ram"
            }
        }
        stage("Run commands"){
            steps {
                sh "date"
                sh """
                ls
                pwd
                date
                """
            }
        }
        stage("Environment Variables"){
            environment {
                username = "surajsgupta"
            }
            steps {
                sh 'echo "Jai Shri Ram"'
                sh '''
                echo "build id - ${BUILD_ID}"
                echo "i am ${name}"
                echo "user is ${username}"
                '''
            }
        }
        stage("Parameters"){
            steps {
                sh 'echo "Jai Shri Ram"'
                sh '''
                echo "person is ${person}"
                echo "active status - ${is_active}"
                echo "city is ${city}"
                '''
            }
        }
        stage("Continue ?"){
            input {
                message "should we continue?"
                ok "yes, we should"
            }
            steps {
                sh 'echo "Jai Shri Ram"'
            }
        }
        stage("Test"){
            steps {
                echo "Test"
                sh '''
                echo "build id - ${BUILD_ID}"
                echo "i am ${name}"
                echo "user is ${username}"
                '''
            }
        }
        stage("Build"){
            steps {
                echo "Build"
            }
        }
        stage("Deploy on Test"){
            steps {
                echo "Deploy on Test"
            }
        }
        stage("Deploy on Production"){
            steps {
                echo "Deploy on Production"
            }
        }
    }
    post {
        success {
            echo "pipeline execution successfull"
        }
        failure {
            echo "pipeline execution failed"
        }
        always {
            echo "Jai Shri Ram"
        }
    }
}
