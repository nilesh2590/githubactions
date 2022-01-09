node {
 def app
 stage(‘Clone repository’) {
 checkout scm
 }
 stage(‘Build image’) {
 app = docker.build(“nilesh2590/githubactions”)
 }
 stage(‘Test image’) {
 app.inside {
 sh ‘echo “Test passed”’
 }
 }
 stage(‘Push image’) {
 docker.withRegistry(‘https://hub.docker.com’, ‘nilesh2590’) {
 app.push("${env.BUILD_NUMBER}")
 app.push(“latest”)
 }
 }
}
