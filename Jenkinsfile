pipeline {
     agent any
     environment {
       CI = true                               //can be used in whole pipeline
     }
     stages {
        stage("Build") {
            steps {
                sh "npm run clean"
                sh "npm install"
                sh "npm run build" 
            }
        }
        stage ("Deploy") {
          sh "ssh ubuntu@3.109.78.90 rm -rf /var/www/html/*"
          sh "ssh ubuntu@3.109.78.90 mkdir -p /var/www/html"
          sh "scp -r dist ubuntu@3.109.78.90:/var/www/html/*"
        }
    }
}
