pipeline{
        agent any
        stages{
            stage('clone directory'){
                steps{
                    sh "git clone  https://gitlab.com/qacdevops/chaperootodo_client"
                }
            }
            stage('install docker and docker compose'){
                steps{
                    sh "curl https://get.docker.com | sudo bash"
                    sh "sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose"
                    sh "sudo chmod +x /usr/local/bin/docker-compose"
                }
            }
            stage('deploy application'){
                steps{
                    sh " sudo docker-compose pull && sudo -E DB_PASSWORD=${DB_PASSWORD} docker-compose up -d"
        }
}
