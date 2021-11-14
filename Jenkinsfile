node {    
      def app     
      
      stage('Clone repository') {               
             
            checkout scm    
      }     
//       stage('Build image') {         
       
//             sh 'docker --version'   
//             app = docker.build("2981984/snake")
//        }     
         
//       stage('Post-to-dockerhub') {
    
//        docker.withRegistry('https://registry.hub.docker.com', 'Docker_credentials') {
//             app.push("latest")
//         			}
//          }
//       stage('Pull-image-server') {
    
//          sh "docker-compose down"
//          sh "docker-compose up -d"	
//       }
      stage('Synk scan') {
            sh 'pwd'
            sh 'snyk test --json | snyk-to-html -o results.html'
            // sh 'mail -s "synk report" anuradhavmane@gmail.com -A results.html'
           // sh 'cat results.html | mailx anuradhavmane@gmail.com'
            //sh '/Users/admin/.jenkins/workspace/pipe'
            sh 'mailx -a /Users/admin/.jenkins/workspace/pipe/results.html -s "Subject" anuradhavmane@gmail.com'
      }
}
