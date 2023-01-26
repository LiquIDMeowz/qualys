pipeline {
    agent  {
        label 'podman'
    }

    stages {
        stage("build image") {
            steps {
                script {
                    sh "cp /home/jenkins/Dockerfile /tmp/workspace/qualys-test/Dockerfile"
                    sh "/usr/bin/podman build -t testingstuff ."
                }
            }
        }
    }
}
