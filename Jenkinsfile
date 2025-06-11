pipeline {
    agent any

    tools {
        maven 'Maven3'      // Match the Maven name in Jenkins' Global Tool Configuration
        jdk 'Java17'        // Match the JDK name in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/your-username/your-repo.git'
            }
        }

        stage('Build') {
            steps {
                dir('demo') {
                    bat 'mvn package'
                }
            }
        }

        stage('Run') {
            steps {
                bat 'mvn exec:java -Dexec.mainClass="com.example.HelloWorld"'
            }
        }
    }

    post {
        failure {
            echo 'Build failed!'
        }
        success {
            echo 'Hello World app ran successfully!'
        }
    }
}
