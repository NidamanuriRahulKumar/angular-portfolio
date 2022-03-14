pipeline {
    agent any
    stages {
        stage('git repo clone') {
            steps {
                git branch: 'main', url: 'https://github.com/NidamanuriRahulKumar/angular-portfolio.git'
            }
        }
        // stage('clean') {
        //     steps {
        //         sh "mvn clean"
        //     }
        // }
        // stage('package') {
        //     steps {
        //         sh "mvn package"
        //     }
        // }
        // stage('docker build') {
        //     steps {
        //         sh "docker build -t employee-management ."
        //     }
        // }
        stage('docker build') {
             steps {
                 sh "docker build"
             }
        }

        stage('docker running') {
             steps {
                 sh "docker container run -d -p 90:90 --name portfolio myportfolio"
             }
        }
    }
}
