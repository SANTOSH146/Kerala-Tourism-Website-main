pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Pull the latest version of the website files from the GitHub repository
                git branch: 'main', url: 'https://github.com/SANTOSH146/Kerala-Tourism-Website-main.git'
            }
        }

        stage('Build') {
            steps {
                // Optional: Build the website if there is any build process
                echo 'No build steps required for this static website'
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Define the path to your XAMPP htdocs directory with correct path separator
                    def xamppHtdocs = 'C:/xampp/htdocs/Tourism_website'

                    // Remove the existing website files
                    bat "rmdir /S /Q ${xamppHtdocs}"

                    // Create the directory if it does not exist
                    bat "mkdir ${xamppHtdocs}"

                    // Copy the new website files to the XAMPP htdocs directory
                    dir('your-website-directory') {
                        bat "xcopy /E /I * ${xamppHtdocs}"
                    }
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
    }
}
