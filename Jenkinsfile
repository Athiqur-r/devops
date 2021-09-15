pipeline {
     agent any
     environment {
       CI = 'false'                               //can be used in whole pipeline
     }
     stages {
        stage("Build") {
            steps {
                bat "npm install"
                bat "npm run build"
            }
        }
    }
}
