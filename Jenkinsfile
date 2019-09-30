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
             sh ' echo $ENVIRONMENT '
             
                  
            }

         }
             
                 
                
       
        
        stage('Job de confirmacion'){
            
            steps{
                
               echo "Realizado exitosamente"
            }
        }
        
    }
   
 }
