library('my-shared-lib') _
pipeline {
    agent any
    stage("Build & Push") {
            steps {
                script {
                    dockerBuildAndPush(
                        imageName: "adservice",
                        registry: "nandini951",
                        registryCreds: "docker-cred"
                    )
                }
            }
        }
}
