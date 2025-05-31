pipeline {
    agent any

    triggers {
        pollSCM('* * * * *') // Poll GitHub every minute
    }

    stages {

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Simulated Maven build
                echo 'Running: mvn clean package'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                // Simulated JUnit and Postman tests
                echo 'Running: mvn test'
                echo 'Running: newman run collection.json'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Running static code analysis...'
                // Simulated SonarQube analysis
                echo 'Running: sonar-scanner'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Simulated OWASP Dependency-Check
                echo 'Running: dependency-check.sh --project my-app --scan .'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying application to staging server...'
                // Simulated SSH or Ansible deployment
                echo 'Running: scp target/my-app.jar user@staging-server:/opt/app'
                echo 'Running: ssh user@staging-server "java -jar /opt/app/my-app.jar"'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
                // Simulated Selenium or Postman test
                echo 'Running: newman run staging-tests.json'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying application to production server...'
                // Simulated production deployment
                echo 'Running: scp target/my-app.jar user@prod-server:/opt/app'
                echo 'Running: ssh user@prod-server "java -jar /opt/app/my-app.jar"'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully.'
        }
        failure {
            echo 'Pipeline failed. Please check logs.'
        }
    }
}
// Trigger test commit for Jenkins task 6