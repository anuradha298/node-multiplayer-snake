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
      stage('Synk scan') {
            cd ${WORKSPACE}
            echo “snyk test and snyk monitor” > snyk.sh
            chmod +x snyk.sh
            /bin/bash snyk.sh || true
            snyk test --json | snyk-to-html -o results.html
      }
}
