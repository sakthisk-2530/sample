pipeline {
    agent {label 'node1'} 

    stages {

        stage('Clone Repository') {
            steps {
                echo "Cloning repo..."
                git 'https://github.com/sakthisk-2530/sample.git'
            }
        }

        stage('List Files') {
            steps {
                echo "Listing files..."
                sh 'ls -l'
            }
        }

        stage('Prepare Directory') {
            steps {
                echo "Preparing directory..."
                sh 'mkdir -p /var/www/html'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying project..."
                sh '''
                rm -rf /var/www/html/*
                cp -r * /var/www/html/
                '''
            }
        }

        stage('Show Endpoint') {
            steps {
                echo "Website URL: http://15.207.54.238"
            }
        }
    }
}
