// Prints a message to the console, your name + whatever you want :-) 
// Checks if the current day is a weekday or weekend
// If it's a weekday, print a message saying "It's a weekday!"
// If it's a weekend, print a message saying "It's the weekend!"
pipeline{
    agent any
    stages{
        stage('Build') {
            steps {
                dir("${env.WORKSPACE}/code"){
                sh 'pwd'
                sh 'npm install'
                }
            }
        }
        stage('SonarQube analysis') {
            steps {
                withSonarQubeEnv('sonarqube-10.0') {
                    script {
                        def scannerHome = tool 'sonar-scanner'
                        sh "${scannerHome}/bin/sonar-scanner \
                            -Dsonar.projectKey=sqp_d5e3d1e77ebf594ada6967f151eccea68a78d599 \
                            -Dsonar.sources=/"
                    }
                }
            }
        }
    }
}