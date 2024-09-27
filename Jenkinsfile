// pipeline {
//     agent any

//     environment {
//         // Replace with your Azure Storage credentials
//         AZURE_STORAGE_ACCOUNT_NAME = 'mystaticweb146'
//         AZURE_STORAGE_CONTAINER_NAME = '$web'
//         AZURE_STORAGE_ACCOUNT_KEY = 'azure-storage-account-key'
//     }

//     stages {
//         stage('Checkout') {
//             steps {
//                 git branch: 'main', url: 'https://github.com/SANTOSH146/Kerala-Tourism-Website-main.git'
//             }
//         }

//         stage('Build') {
//             steps {
//                 echo 'No build steps required for this static website'
//             }
//         }

//         stage('Check Tools') {
//             steps {
//                 sh 'echo %PATH%'
//                 sh 'htmlhint --version'
//             }
//         }


//         // stage('Test') {
//         //     steps {
//         //         script {
//         //             // Example: Running HTML validation using a tool like HTMLHint or a linter or 
//         //             bat 'htmlhint "**/*.html"'

//         //             // Example: Running CSS validation
//         //             bat 'stylelint "**/*.css"'

//         //             // Example: Running JavaScript tests (if applicable)
//         //             //bat 'eslint "**/*.js"'

//         //             // You can add more tests or validations as needed
//         //         }
//         //     }
//         // }

//         stage('Install Azure CLI') {
//             steps {
//                 script {
//                     // Install Azure CLI (if not already installed)
//                     sh 'curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash'
//                 }
//             }
//         }

//         stage('Upload to Azure Blob Storage') {
//             steps {
//                 script {
//                     // Upload files to Azure Blob Storage
//                     sh '''
//                     az storage blob upload-batch \
//                         --account-name $AZURE_STORAGE_ACCOUNT_NAME \
//                         --account-key $AZURE_STORAGE_ACCOUNT_KEY \
//                         --destination $AZURE_STORAGE_CONTAINER_NAME \
//                         --source ./
//                     '''
//                 }
//             }
//         }
//     }

//     post {
//         success {
//             echo 'Deployment completed successfully.'
//         }
//         failure {
//             echo 'Deployment failed.'
//         }
//         always {
//             // Always run this block, even if the pipeline fails or succeeds
//             echo 'Pipeline finished.'
//         }
//     }
// }

pipeline {
    agent any
    
    stages {
        stage('Checkout Code') {
            steps {
                echo 'Checking out code...'
                git branch: 'main', url: 'https://github.com/SANTOSH146/Kerala-Tourism-Website-main.git'
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'echo "This is a placeholder for the build process."'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running tests...'
                sh 'echo "Running sample tests to ensure pipeline is working."'
            }
        }

        stage('Deployment') {
            steps {
                echo 'Deploying the application...'
                sh 'echo "This is a placeholder for the deployment process."'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}

