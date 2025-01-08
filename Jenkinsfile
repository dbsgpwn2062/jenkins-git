node {
    stage('Clone repository') {
        git credentialsId: 'github-access', url: 'https://github.com/dbsgpwn2062/jenkins-git.git', branch: 'main'
    }

    stage('Build image') {
        dockerImage = docker.build("dbsgpwn2062/node-front:1.0")
    }

    stage('Push image') {
        withDockerRegistry([credentialsId: "docker-access", url: ""]) {
            dockerImage.push()
        }
    }
}

