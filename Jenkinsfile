node {
    stage('Clone repository') {
        git credentialsId: 'github_access_token', url: 'https://github.com/bsd9115/webCount.git', branch: 'main'
    }

    stage('Build image') {
       dockerImage = docker.build("bsd9115/webcount:v1.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}
