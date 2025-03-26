pipeline{
    agent any
    stages {
        stage('Build') {
            steps {
               sh "mvn clean package" 
            }
        }
        stage('Deploy') {
            steps {
                deploy adapters: [tomcat7(credentialsId: 'cdd3315e-632b-4021-9cea-40cb889a7012', path: '', url: 'http://ec2-52-91-190-28.compute-1.amazonaws.com:8080/')], contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
