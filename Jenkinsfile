pipeline {
    agent  {
        label 'podman'
    }

    stages {
        stage("build image") {
            steps {
                script {
                    sh "podman build https://github.com/LiquIDMeowz/image"
                }
            }
        }
    }
}
