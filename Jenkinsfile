node {    
      def app     
      
      stage('Clone repository') {               
             
            checkout scm    
      }     
      stage('Build image') {         
       
            sh 'docker --version'   
            app = docker.build("2981984/snake")
       }     
         
      stage('Post-to-dockerhub') {
    
       docker.withRegistry('https://registry.hub.docker.com', 'Docker_credentials') {
            app.push("latest")
        			}
         }
      stage('Pull-image-server') {
    
         sh "docker-compose down"
         sh "docker-compose up -d"	
      }
}
