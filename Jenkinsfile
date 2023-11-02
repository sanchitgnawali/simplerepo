pipeline {
    agent any
    
    stages {
        stage("Build") {
            steps {
                sh 'mvn clean package'
            }
        }
        stage("Deploy") {
            steps {
                deploy adapters: [tomcat9(credentialsId: '9c3f6726-1e2d-4736-99bd-69784a33dd8d', path: '', url: 'http://ec2-54-174-234-160.compute-1.amazonaws.com:8080/')], 
                contextPath: 'webapp', 
                war: '**/java-web-project'
            }
        }
    }
}
