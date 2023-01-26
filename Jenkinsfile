pipeline {
    agent  {
        label 'podman'
    }

    stages {
        stage("build image") {
            steps {
                script {
                    sh "cd /home/jenkins"
                    sh "/usr/bin/podman build -t testingstuff ."
                }
            }
        }
    }
}
