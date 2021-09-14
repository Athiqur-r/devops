pipeline {
     agent any
     stages {
        stage("Build") {
            steps {
                bat "npm install"
                bat "npm run build"
            }
        }
        stage("Deploy") {
            steps {
                bat "rmdir /s /q /jenkins-react-app"
                bat "cp -r ${WORKSPACE}/build/ /jenkins-react-app/"
            }
        }
    }
}
