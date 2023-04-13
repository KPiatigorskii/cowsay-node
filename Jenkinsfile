// Prints a message to the console, your name + whatever you want :-) 
// Checks if the current day is a weekday or weekend
// If it's a weekday, print a message saying "It's a weekday!"
// If it's a weekend, print a message saying "It's the weekend!"
pipeline{
    agent any
    tools{
        nodejs: 'node-19.9.0'
    }
    stages{
        stage('Build') {
            steps {
                dir("${env.WORKSPACE}/code"){
                sh 'pwd'
                sh 'npm install'
                sh 'nvm install 14.17'
                }
            }
        }
        stage('SonarQube analysis') {
            steps {
                withSonarQubeEnv('sonarqube-10.0') {
                    script {
                        def scannerHome = tool 'SonarQubeScanner-4.8'
                        sh "${scannerHome}/bin/sonar-scanner \
                            -Dsonar.projectKey=sqp_d5e3d1e77ebf594ada6967f151eccea68a78d599 \
                            -Dsonar.sources=/${env.WORKSPACE}/code"
                    }
                }
            }
        }
    }
}