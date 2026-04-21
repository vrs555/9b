EXP-19

create a folder and Dockerfile and app.py 

Add:

git init
git remote add origin <git_repo> 
git add .
git commit
git push -u origin master 

In Jenkins 
open pipeline and add scripts


pipeline {
    agent any
    stages {
        stage('Clone Code') {
            steps {
                git '<your-repo>'
            }
        }
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t my-app .'
            }
        }
        stage('Run Container') {
            steps {
                bat 'docker run -d my-app'
            }
        }
    }
}

save and build 
