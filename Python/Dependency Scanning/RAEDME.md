@Library('Jenkins-shared-libraries@main') _  // Replace with your library name

pipeline {
    agent any

    environment {
        DEP_CHECK_PATH = '/opt/dependency-check/bin'  // Path to the Dependency-Check installation
        DEP_CHECK_REPORT_PATH = '/tmp/dependency-check-report.html'  // Path for the report
        TEMP_REPORT_PATH = '/tmp/dependency-check-report-temp.html'  // Temporary file path for email
    }

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    python_clone_repo()  // Ensure this method is defined in your shared library
                }
            }
        }

        stage('Set Up Python Environment') {
            steps {
                script {
                    python_environment()  // Ensure this method is defined in your shared library
                }
            }
        }

        stage('Poetry Lock') {
            steps {
                script {
                    poetry_lock()  // Ensure this method is defined in your shared library
                }
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    python_dependencies()  // Ensure this method is defined in your shared library
                }
            }
        }

        stage('Install OWASP Dependency-Check') {
            steps {
                script {
                    installation_owsap()  // Ensure this method is defined in your shared library
                }
            }
        }

        stage('Update OWASP Dependency-Check Scan') {
            steps {
                script {
                    update_owsap()  // Ensure this method is defined in your shared library
                }
            }
        }

        stage('Run OWASP Dependency-Check Scanning') {
            steps {
                script {
                    scanning_owsap()  // Ensure this method is defined in your shared library
                }
            }
        }

        stage('Archive Dependency Check Report') {
            steps {
                // Archive the dependency-check HTML report as an artifact
                archiveArtifacts allowEmptyArchive: true, artifacts: 'dependency-check-report.html', onlyIfSuccessful: true
            }
        }

        stage('Send Dependency Check Report Email') {
            steps {
                script {
                    // Copy the report to a safe location if needed (avoiding overwriting the same file)
                    sh "cp '${DEP_CHECK_REPORT_PATH}' '${TEMP_REPORT_PATH}'"  // Copy to a new temp location

                    // Send email with the Dependency-Check report as an attachment
                    emailext(
                        to: 'anjalidhiman.as@gmail.com',  // Replace with actual recipient
                        subject: "OWASP Dependency-Check Report - ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                        body: "Please find the attached Dependency-Check report for ${env.JOB_NAME} #${env.BUILD_NUMBER}.",
                        attachmentsPattern: '${TEMP_REPORT_PATH}',  // Path to the temporary report file
                        mimeType: 'text/html'
                    )
                }
            }
        }
    }
}
