pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/SardarMuhammadAhsanKhan/Grocermate.git'
            }
        }

        stage('Check Workspace') {
            steps {
                sh '''
                    echo "Current directory:"
                    pwd
                    echo "Listing files:"
                    ls -l
                '''
            }
        }

        stage('Deploy Static HTML') {
            steps {
                sh '''
                    sudo mkdir -p /var/www/html
                    sudo rm -rf /var/www/html/*
                    if [ -f index.html ]; then
                        sudo cp index.html /var/www/html/index.html
                        echo "index.html copied successfully"
                    else
                        echo "ERROR: index.html not found in workspace"
                        exit 1
                    fi
                '''
            }
        }
    }

    triggers {
        githubPush()
    }
}
