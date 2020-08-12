pipeline {
    agent any
    stages {
        stage ('Build') {
            steps {
                sh "mvn clean package"
            }
        }
        stage ('Deploy') {
            steps {
                deploy adapters: [tomcat7(credentialsId: '911a69f9-debd-4797-82b0-0bc024b9d362', 
                path: '', url: 'http://ec2-52-15-76-148.us-east-2.compute.amazonaws.com:8080/')], 
                contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }

    }
}
