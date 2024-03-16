node {
  stage('Clone repository') {
    git credentialsId: 'github_access_token', url: 'https://github.com/honganja/jenkins-mydiary-msa.git'
  }
  stage('Build image') {
    dockerImage = docker.build("honganja/mydiary-front:3.0")
  }
  stage('Push image') {
    withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
    dockerImage.push()
    }
  }
}
