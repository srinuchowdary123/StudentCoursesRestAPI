pipeline {
    agent any
    triggers { 
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/khajadevopsmarch23/StudentCoursesRestAPI',
                    branch: 'develop'
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
