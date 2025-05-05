pipeline {
    agent any
    
    environment {
        NODE_ENV = 'production'
    }

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Cloning repository...'
                git url: 'https://github.com/vimleshmourya05/ReactTodoUIMonolith.git', branch: 'main'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing NPM dependencies...'
                sh 'npm install'
            }
        }

        stage('Build React App') {
            steps {
                echo 'Installing NPM dependencies...'
                sh 'npm run build'
            }
        }

        stage('Archive Build Artifacts') {
            steps {
                echo 'Archiving production build...'
                archiveArtifacts artifacts: 'build/**', allowEmptyArchive: false
            }
        }
    }

    post {
        success {
            echo '✅ Build completed successfully.'
        }
        failure {
            echo '❌ Build failed.'
        }
    }
}
