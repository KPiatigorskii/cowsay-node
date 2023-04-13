// Prints a message to the console, your name + whatever you want :-) 
// Checks if the current day is a weekday or weekend
// If it's a weekday, print a message saying "It's a weekday!"
// If it's a weekend, print a message saying "It's the weekend!"
pipeline{
    agent none
    stages{
        stage("Prints a message to the console, your name + whatever you want"){
            steps{
                echo "Kosta, you forgot all about jenkins! HOW DARE YOU???"
            }
        }
        stage("Checks if the current day is a weekday or weekend"){
            steps{
                if (( \$(date +%u) > 5 )); then
                    echo "It's the weekend!";
                else
                    echo "It's a weekday!"; 
                fi
            }
        }
    }
}