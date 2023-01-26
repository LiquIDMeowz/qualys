pipeline {
    agent  {
        label 'podman'
    }

    stages {
        stage("build image") {
            steps {
                script {
                    sh "cp /home/jenkins/Dockerfile /tmp/workspace/qualys-test/Dockerfile"
                    sh "cd /tmp/workspace/qualys-test/"
                    sh "/usr/bin/podman build -t testingstuff . --build-arg http_proxy=http://138.35.24.153:8088 --build-arg https_proxy=http://138.35.24.153:8088 --build-arg HTTPS_PROXY=http://138.35.24.153:8088 --build-arg HTTP_PROXY=http://138.35.24.153:8088"
                }
            }
        }
    }
}
