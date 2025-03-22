pipeline {
    agent {
        node {
            label "dev"
        }
    }

    // Trigger the pipeline every 5 minutes if there are changes in the repository
    triggers {
        pollSCM('H/20 * * * *')
    }

    stages {
        stage("Clone Code") {
            steps {
                git url: "https://github.com/sudiptarathi2020/flask-student-attendance-app.git", branch: "main"
                echo "Cloning code from GitHub"
            }
        }

        stage("Build and Deploy") {
            steps {
                sh "docker compose down && docker compose up -d"
                echo "Build and deploy"
            }
        }
    }
}
