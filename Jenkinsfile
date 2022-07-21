node{
    
    def mavenHome = tool name: 'Maven 3.8.6'
    stage('scm clone'){
        
        git branch: 'main', url: 'https://github.com/upd1311/docker_project.git'
    }
    
    stage('Build Docker Image'){
        sh 'docker build -t upd1311/abc . '
    }
    stage ('Image push'){
        withCredentials([string(credentialsId: 'Dockerhubcredentials', variable: 'Dockerhubcredentials')]) {
            sh 'docker login -u upd1311 -p ${Dockerhubcredentials}'

}
     sh 'docker push upd1311/abc'
        
    }
    stage('Build Container'){
        
        
         
            sh 'docker run -p 82:80 -d --name upd2 upd1311/abc'
			
   
    }
    
}
