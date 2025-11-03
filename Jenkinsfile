pipeline {
    agent any // Or a specific agent label

    stages {
        stage('Checkout Code') {
            steps {
                git 'your_repository_url' // Replace with your Git repository URL
            }
        }
        stage('Terraform Init') {
            steps {
                sh 'terraform init'
            }
        }
        stage('Terraform Plan') {
            steps {
                sh 'terraform plan -out=tfplan' // Creates a plan file
            }
        }
        stage('Terraform Apply') {
            steps {
                input {
                    message "Proceed with Terraform Apply?"
                    ok "Apply"
                }
                sh 'terraform apply tfplan' // Applies the plan
            }
        }
    }
}