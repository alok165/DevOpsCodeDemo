
pipeline{
    tools{
       
        maven 'mymaven'
    }
	//agent any
    agent {label 'linux_node'}

      stages{
           stage('Checkout'){
	    
               steps{
		 echo 'cloning'
                  git 'https://github.com/alok165/DevOpsCodeDemo.git'
              }
          }
          stage('Compile'){
             
              steps{
                  echo 'complie the code..'
                  sh 'mvn compile'
	      }
          }
          stage('CodeReview'){
		  
              steps{
		    
		  echo 'codeReview'
                  sh 'mvn pmd:pmd'
              }
          }
           stage('UnitTest'){
		  
              steps{
	         
                  sh 'mvn test'
              }
          
          }
         agent {label 'linux_node2'}
          stage('Package'){
		  
              steps{
		          echo 'packing'
                  sh 'mvn package'
              }
          }
	     
          
      }
}
