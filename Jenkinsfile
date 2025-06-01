pipeline {
    agent any

    tools {
        maven 'MAVEN_HOME'
        jdk 'JDK_HOME'
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
