pipeline {
    agent any

    stage('Clone Repository') {
    steps {
        git branch: 'main', url: 'https://github.com/SardarMuhammadAhsanKhan/Grocermate.git'
    }
}

        }

        stage('Deploy Static HTML') {
            steps {
                sh '''
                sudo rm -rf /var/www/html/*
                sudo cp index.html /var/www/html/index.html
                '''
            }
        }
    }

    triggers {
        githubPush()
    }
}
