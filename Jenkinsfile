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
             
             sh '''
             cp /var/lib/jenkins/workspace/Job_secundario_test/output/somefile .
             export ENVIRONMENT=$(sed -n '1p' somefile)
             echo  "Hola este es el ambiente en el que se esta trabajando $ENVIRONMENT"   
             '''
            }

         }
     }
   
 }
