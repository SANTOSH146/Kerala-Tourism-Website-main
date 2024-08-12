stage('Deploy') {
    steps {
        script {
            // Define the path to your XAMPP htdocs directory
            def xamppHtdocs = 'C:/xampp/htdocs/Tourism_website'
            def websiteDir = 'your-website-directory'

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
            dir(websiteDir) {
                bat "xcopy /E /I /Y * ${xamppHtdocs}"
            }
        }
    }
}
