pipeline {
    agent any
    stages {
        stage('git repo clone') {
            steps {
                git branch: 'main', url: 'https://github.com/NidamanuriRahulKumar/angular-portfolio.git'
            }
        }
        stage('npm install') {
             steps {
                 sh "npm install"
             }
         }
         stage('ng build') {
             steps {
                 sh "ng build"
             }
         }
        // stage('docker build') {
        //     steps {
        //         sh "docker build -t employee-management ."
        //     }
        // }
        stage('docker build') {
             steps {
                 sh "docker build -t angular-portfolio"
             }
        }

        stage('docker running') {
             steps {
                 sh "docker container run -d -p 90:90 --name portfolio angular-portfolio"
             }
        }
    }
}
