pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/SANTOSH146/Kerala-Tourism-Website-main.git'
            }
        }

        stage('Build') {
            steps {
                echo 'No build steps required for this static website'
            }
        }

        stage('Test') {
            steps {
                script {
                    // Example: Running HTML validation using a tool like HTMLHint or a linter
                    bat 'htmlhint "**/*.html"'

                    // Example: Running CSS validation
                    bat 'stylelint "**/*.css"'

                    // Example: Running JavaScript tests (if applicable)
                    bat 'eslint "**/*.js"'

                    // You can add more tests or validations as needed
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    def xamppHtdocs = 'C:/xampp/htdocs/Tourism_website'
                    def websiteDir = "${env.WORKSPACE}"

                    bat """
                    if exist "${xamppHtdocs}" (
                        echo Deleting existing files...
                        rd /S /Q "${xamppHtdocs}"
                    )
                    """
                    bat "mkdir \"${xamppHtdocs}\""
                    bat """
                    xcopy "${websiteDir}\\*" "${xamppHtdocs}\\" /E /I /Y
                    """
                }
            }
        }
    }

    post {
        success {
            echo 'Deployment completed successfully.'
        }
        failure {
            echo 'Deployment failed.'
        }
        always {
            // Always run this block, even if the pipeline fails or succeeds
            echo 'Pipeline finished.'
        }
    }
}
