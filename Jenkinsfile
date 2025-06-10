pipeline {
    agent any
    stages {
        stage('Build Application') {
            steps {
                bat 'mvn clean install'
            }
        }
        stage('Deploy CloudHubs') {
            environment {
                ANYPOINT_CREDENTIALS = credentials('74184bb6-fee2-4741-bfac-828bfb61d686')
            }
            steps {
                echo 'Deploying mule project due to the latest code commit…'
                echo 'Deploying to the configured environment….'
                bat "mvn clean deploy -DmuleDeploy -Dmule.app.applicationName=cicd-training -DappName=cicd-training -Dusername=Tale -Dpassword=Mule@1234 -DtargetName=Cloudhub-US-East-2 -Denvironment=sandbox -DmuleVersion=4.8.1"
            }
        }
    }
}
