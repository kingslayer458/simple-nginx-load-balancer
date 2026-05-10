pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                withCredentials([string(credentialsId: 'niggerip', variable: 'niggerip')]) {
                    sshagent(['nigger']) {
                        sh '''
                        ssh -o StrictHostKeyChecking=no ubuntu@$niggerip "
                            cd /home/mrlightsail/simple-nginx-load-balancer &&

                            echo '[+] Deploying...' &&

                            git fetch origin &&
                            git reset --hard origin/main &&

                            docker compose down &&
                            docker compose up -d --build &&

                            echo '[+] Deployment complete'
                        "
                        '''
                    }
                }
            }
        }
    }
}
