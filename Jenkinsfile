pipeline {
    agent any
    environment {
        DISCORD_WEBHOOK = credentials('discord-webhook-test')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post {
        always {
            discordSend description: "Jenkins Pipeline Build", footer: "TJDuncan", link: env.BUILD_URL, result: currentBuild.currentResult, title: JOB_NAME, webhookURL: "$DISCORD_WEBHOOK"
        }
    }
}
