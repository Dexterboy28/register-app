pipeline {
    agent any

    tools {
        maven "maven3"
         jdk 'Java17'
    }

    stages {
        stage("Checkout from SCM") {
            steps {
                git branch: 'main', url: 'https://github.com/Dexterboy28/register-app'
            }
        }

        stage("Build Application") {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }

        stage("Test Application") {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        always {
            echo "Pipeline execution complete."
        }
    }
}
