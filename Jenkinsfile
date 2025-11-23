library('my-shared-lib') _
pipeline {
    agent any
    stages {
        stage("Build & Push") {
            steps {
                script {
                    dockerBuildAndPush(
                        imageName: "productcatalogservice",
                        registry: "nandini951",
                        registryCreds: "docker-cred"
                    )
                }
            }
        }
    }
}
