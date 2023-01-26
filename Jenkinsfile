pipeline {
    agent  {
        label 'podman'
    }

    stages {
        stage("build image") {
            steps {
                script {
                    sh "podman build -t agent-test ."
                }
            }
        }
    }
}
