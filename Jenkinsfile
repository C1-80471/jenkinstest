pipeline {
    agent any
    stages {
        stage ('build docker image') {
            steps {
                sh '/usr/bin/docker image build -t pravin1015/jenkinsdemo .'
            }
        }
        stage ('docker login') {
            steps {
                sh 'echo dckr_pat_qadgYsLNo981IzgC1s4EtZpBdHY | /usr/bin/docker login -u pravin1015 --password-stdin'
            }
        }
        stage ('push docker image') {
            steps {
                sh '/usr/bin/docker image push pravin1015/jenkinsdemo'
            }
        }
        stage ('reload docker service') {
            steps {
                sh '/usr/bin/docker service update --image pravin1015/jenkinsdemo --force myservice'
            }
        }

    }
}

