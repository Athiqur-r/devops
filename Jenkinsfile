pipeline {
     agent any
     environment {
        CI = 'true'
     }
     stages {
        stage("Build") {
            steps {
                sh "npm install"
                sh "npm run build" 
            }
        }
        stage ("Deploy") {
             steps {
                  sh "ssh -i 'idmt-dev.pem' ubuntu@ec2-3-109-78-90.ap-south-1.compute.amazonaws.com"
                  sh "ssh ubuntu@3.109.78.90 rm -rf /var/www/html/*"
                  sh "ssh ubuntu@3.109.78.90 mkdir -p /var/www/html"
                  sh "scp -r dist ubuntu@3.109.78.90:/var/www/html/*"
             }
        }
    }
}
