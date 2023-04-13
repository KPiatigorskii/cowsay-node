// Prints a message to the console, your name + whatever you want :-) 
// Checks if the current day is a weekday or weekend
// If it's a weekday, print a message saying "It's a weekday!"
// If it's a weekend, print a message saying "It's the weekend!"
pipeline{
    agent any
    tools {
        sonarqubeScanner 'SonarQube'
    }
    stages{
        stage('Build') {
            steps {
                sh cd code
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage('Code analysis') {
            steps {
                sh 'sonar-scanner'
            }
        }
    }
}