@Library("shared-library") _
pipeline{
    agent {label "fighter"}
    
    stages{
        
        stage("Hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        
        stage("code"){
            steps{
              script{
              clone("https://github.com/ShwetaMG/django-demo-notes-app.git","main")
              }
            }
        }
        
        stage("build"){
            steps{
               script{
                   build("notes-app", "leatest", "shwetamg20")
               }
            }
        }
        
         stage("pushing to dockerhub"){
            steps{
               script{
                   push("shwetamg20", "notes-app", "latest")
               }
             }
         }
        
        
        stage("test"){
            steps{
              echo "testing the code "  
            }
        }
        
        stage("deploy"){
            steps{
                script{
                    deploy()
                }
            }
        }
       
            
      }
   }
