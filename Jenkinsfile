node{

    stage('SCM Checkout')
    {
        git url: 'https://github.com/shubhsharm/phpmysql-app.git'
    }
    
    stage('Run Docker Compose File')
    {
        sh 'sudo docker-compose build'
        sh 'sudo docker-compose up -d'
    }
    stage('PUSH image to Docker Hub') 
        {
            sh "sudo docker login -u 08170 -p ${DHPWD}"
            sh 'sudo docker push 08170/phpapp:7.3.3'
        }
}
