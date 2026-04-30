pipeline {
    agent {label 'node1'} 

    triggers {          
        githubPush()
    }

    stages {

        stage('Clone Repository') {
            steps {
                sh 'rm -rf sample'
                sh 'git clone https://github.com/sakthisk-2530/sample.git'
            }
        }

        stage('List Files') {
            steps {
                sh 'ls -l sample'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                rm -rf /var/www/html/*
                cp -r sample/* /var/www/html/
                '''
            }
        }

        stage('Reload Nginx') {
            steps {
                sh 'sudo systemctl restart nginx'
            }
        }

        stage('Show Endpoint') {
            steps {
                echo "http://13.201.123.45"
            }
        }
    }
}
