pipeline{
    agent any
     
    stages{
        
        stage('Job primario de test'){
            
            steps{
                
                build job: 'Job_secundario_test', wait: true
            }
        }
         stage('Job de cambio de variables'){
            
            steps{
               
             

             sh 'cp /var/lib/jenkins/workspace/Job_secundario_test/output/somefile .'
             sh 'ENVIRONMENT=$(cat somefile)'
             sh 'export ambiente=$ENVIRONMENT'
                    
             echo $ambiente
            }

         }
             
                 
               
       
        
       stage ('Remove inactive environment tables PROD-A') {
            when {
            expression { $ENVIRONMENT == 'Development' }
            }
              steps {
                echo "Removing the inactive environment tables from PROD-B"
               
              }
            }
    }
   
 }
