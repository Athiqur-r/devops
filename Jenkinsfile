pipeline {
     agent any
     tools {nodejs "nodejs"}
     stages {
        stage("Build") {
            steps {
                sh "npm install"
                sh "npm run build" 
            }
        }
        stage ("Deploy") {
             steps {
                  sh "ssh ubuntu@3.109.78.90 rm -rf /var/www/html/*"
                  sh "ssh ubuntu@3.109.78.90 mkdir -p /var/www/html"
                  sh "scp -r dist ubuntu@3.109.78.90:/var/www/html/*"
             }
        }
    }
}
