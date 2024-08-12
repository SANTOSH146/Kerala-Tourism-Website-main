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
                    // Define the path to your XAMPP htdocs directory
                    def xamppHtdocs = 'C:/xampp/htdocs/Tourism_website'
                    def websiteDir = "${env.WORKSPACE}"  // Automatically points to the current workspace directory

                    // Remove the existing website files if the directory exists
                    bat """
                    if exist "${xamppHtdocs}" (
                        echo Deleting existing files...
                        rd /S /Q "${xamppHtdocs}"
                    )
                    """

                    // Create the directory
                    bat "mkdir \"${xamppHtdocs}\""

                    // Copy the new website files to the XAMPP htdocs directory
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
    }
}
