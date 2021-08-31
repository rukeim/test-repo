node {
     stage('Clone') {
         checkout scm
     }
     stage('Build') {
         app = docker.build("shout685/test-repo")  # 빌드할 이미지명은 자신의 Docker Hub 계정을 넣어주어야 합니다.
		   				   # app = docker.build("<계정명>/<저장소명>")
     }
     stage('Push') {
         docker.withRegistry('https://registry.hub.docker.com', 'docker_hub') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
 }
