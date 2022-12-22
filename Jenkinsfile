node{

    stage('SCM Checkout')
    {
        git credentialsId: '24b2aed2-c7f7-42ff-8864-8ca6c9871f05', url: 'https://github.com/milindsagar/online-shop.git'
    }
    
    stage('Run Docker Compose File')
    {
        sh 'sudo docker-compose build'
        sh 'sudo docker-compose up -d'
    }
    stage('PUSH image to Docker Hub')
    {
      /* withCredentials([string(credentialsId: 'DockerHubPassword', variable: 'DHPWD')]) 
        {
            sh "docker login -u sagartestdocker -p ${DHPWD}"
        }
        sh 'docker push vardhanns/phpmysql_app'
        */
        //docker.withRegistry( 'https://registry.hub.docker.com', 'DockerHubPassword' ) {
             
             sh 'sudo docker login -u "sagartestdocker" -p "sagar@123" docker.io'
             //sh 'sudo docker push sagartestdocker/mysql'
             //sh 'sudo docker push sagartestdocker/job1_web1.0'
             sh 'sudo docker push sagartestdocker/job1_web2.0'
            // sh 'docker push sagartestdocker/mysql'
          
    }
}
