pipeline {
    agent  {
        label 'podman'
    }

    stages {
        stage("build image") {
            steps {
                script {
                    withCredentials([usernamePassword(credentialsId: 'd4025996-d470-4a8a-b21e-5550da91c5fe', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                        sh "cp /home/jenkins/Dockerfile /tmp/workspace/qualys-test/Dockerfile"
                        sh "cd /tmp/workspace/qualys-test/"
                        sh "podman login -u $USERNAME -p $PASSWORD default-route-openshift-image-registry.apps.sbx.advantagedp.org"
                        sh "/usr/bin/podman build -t testingstuff --device /dev/fuse ."
                    }
                }
            }
        }
    }
}
