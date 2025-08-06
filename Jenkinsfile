pipeline {
    agent any

    environment {
        GIT_REPO = 'https://github.com/YeshwanthYolar/jenkins-pipeline.git'
        BRANCH = 'main'
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: "${BRANCH}", url: "${GIT_REPO}"
            }
        }

        stage('Copy index.html') {
            steps {
                script {
                    sh '''
                    if [ -f index.html ]; then
                        sudo cp index.html /var/www/html/
                        echo "index.html copied to /var/www/html"
                    else
                        echo "index.html not found in repo"
                        exit 1
                    fi
                    '''
                }
            }
        }
    }
}
