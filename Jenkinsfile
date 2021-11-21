node{

    stage('SCM Checkout')
    {
        git url: 'https://github.com/shubhsharm/phpmysql-app'
    }
    
    stage('Run Docker Compose File')
    {
        sh 'sudo docker-compose build'
        sh 'sudo docker-compose up -d'
    }
    stage('PUSH image to Docker Hub')
    {
        withCredentials([string(credentialsId: 'DockerHubPassword', variable: 'DHPWD')]) 
        {
            sh "docker login -u 08170 -p ${DHPWD}"
        }
        sh 'docker push 08170/phpapp:7.3.3'
    }
}
