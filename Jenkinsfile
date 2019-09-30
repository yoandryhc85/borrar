pipeline{
    agent any
    environment{
        ENVIRONMENT=$(cat somefile)
    
    }
    
    
    stages{
        
        stage('Job primario de test'){
            
            steps{
                
                build job: 'Job_secundario_test', wait: true
            }
        }
         stage('Job de cambio de variables'){
            
            steps{
               
             

             sh 'cp /var/lib/jenkins/workspace/Job_secundario_test/output/somefile .'
             echo "$ENVIRONMENT"
             
                  
            }

         }
             
                 
                
       
        
        stage('Job de confirmacion'){
            
            steps{
                
               echo "Realizado exitosamente"
            }
        }
        
    }
   
 }
