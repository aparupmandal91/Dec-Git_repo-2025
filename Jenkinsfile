pipeline {
    agent any

    stages {
        stage('Update UID') {
            steps {
                script {
                    // Replace UID=2255 with UID=5577 inside the file
                    sh """
                    sed -i 's/UID=2233/UID=5577/' UID.txt
                    """
                }
            }
        }

        stage('Commit & Push') {
            steps {
                sh """
                git config user.email "jenkins@example.com"
                git config user.name "Jenkins"

                git add yourfile.txt
                git commit -m "Auto-update UID to 5577 via Jenkins"
                git push origin main
                """
            }
        }
    }
}
