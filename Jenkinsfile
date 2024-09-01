pipeline {
    agent any

   stages {
        stage('Test') {
            steps {
                sh 'cd SampleWebApp && mvn test'
            }
        }
        stage('Build') {
            steps {
                sh 'cd SampleWebApp && mvn clean package'
            }
        }
        
        stage('Deploy to Tomcat') {
            steps {
deploy adapters: [tomcat9(credentialsId: 'tompass', path: '', url: 'http://34.201.92.68:8080/')], contextPath: 'myapp', war: '**/*.war'            }
        }
    }
}
