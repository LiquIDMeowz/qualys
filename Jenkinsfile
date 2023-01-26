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
                        sh "/usr/bin/podman build -t testingstuff . "
                    }
                }
            }
        }
    }
}

withCredentials([usernamePassword(credentialsId: 'amazon', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
  // available as an env variable, but will be masked if you try to print it out any which way
  // note: single quotes prevent Groovy interpolation; expansion is by Bourne Shell, which is what you want
  sh 'echo $PASSWORD'
  // also available as a Groovy variable
  echo USERNAME
  // or inside double quotes for string interpolation
  echo "username is $USERNAME"
}
