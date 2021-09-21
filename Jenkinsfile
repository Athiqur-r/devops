pipeline {
     agent any
     environment {
       CI = true                               //can be used in whole pipeline
     }
     stages {
        stage("Build") {
            steps {
                sh "npm install"
                sh "npm run build"
            }
        }
    }
}
