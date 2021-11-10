node('master'){  
    agent any
    def app
    stage('Cloning Git') {
        /* Let's make sure we have the repository cloned to our workspace */
       checkout scm
    }  
    
   

    
    stage('Build-and-Tag') {
    /* This builds the actual image; synonymous to
         * docker build on the command line */
        sh 'docker --version'
        echo "Image build successfully"
    }
    
    
    
}
    
