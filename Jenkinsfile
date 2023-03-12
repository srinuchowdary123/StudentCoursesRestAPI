pipeline {
    agent any
    triggers { 
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/srinuchowdary123/StudentCoursesRestAPI.git',
                    branch: 'sprint'
            }
        }
        stage('build') {
            steps {
                sh 'docker image build -t srinunuthi/spc:latest .'
            }
        }
        stage('scan and push') {
            steps {
                sh 'echo docker scan is doing on srinunuthi/spc:latest'
                sh 'docker image push srinunuthi/spc:latest'
            }
        }
    }

}
