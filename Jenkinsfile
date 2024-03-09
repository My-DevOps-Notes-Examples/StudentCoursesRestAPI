pipeline {
    agent { label 'Docker_Node' }
    triggers { pollSCM('* * * * *') }
    stages {
        stage('VCS') {
            steps {
                git url: 'https://github.com/My-DevOps-Notes-Examples/StudentCoursesRestAPI.git',
                    branch: 'develop'
            }
        }
        stage('Build') {
            steps {
                sh 'docker image build -t nagasuribabukola/studentcource:latest .'
            }
        }
        stage('Push') {
            steps {
                sh 'docker image push nagasuribabukola/studentcource:latest'
            }
        }
    }
}