pipeline {
    agent any

    stages {
        stage("1st stage: checkout the code from GitHub") {
            steps {
                git url: "https://github.com/Abhisheksingh67126/addressbook-cicd-project.git"
            }
        }

        stage("2nd stage: compile the code") {
            steps {
                sh "mvn compile"
            }
        }

        stage("3rd stage: testing the code") {
            steps {
                sh "mvn test"
            }
        }

        stage("4th stage: quality assurance of the code") {
            steps {
                sh "mvn pmd:pmd"
            }
        }

        stage("5th stage: package the project") {
            steps {
                sh "mvn package"
            }
        }

       stage("6th stage: deploy the project") {
            steps {
                sh 'sudo cp "$WORKSPACE/target/addressbook.war" /opt/tomcat/webapps/'
                sh 'sudo systemctl restart tomcat'
            }
        }
    }
}
