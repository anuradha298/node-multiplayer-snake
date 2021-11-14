node {    
      def app     
      
      stage('Clone repository') {               
             
            checkout scm    
      }     
      stage('Build image') {         
       
            sh 'docker --version'   
            app = docker.build("2981984/snake")
       }     
         
}
