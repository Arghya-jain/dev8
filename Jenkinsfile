pipeline {
    agent any

    tools {
        maven 'Maven3'       // Make sure this matches the name in Jenkins → Global Tool Configuration
        jdk 'OpenJDK11'           // Make sure this matches the name in Jenkins → Global Tool Configuration
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy') {
            steps {
                sh 'ansible-playbook -i ansible/inventory ansible/deploy.yml'
            }
        }
    }
}

