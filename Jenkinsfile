
pipeline{
    tools{
       
        maven 'mymaven'
    }
	//agent any
    agent none

      stages{
           stage('Checkout'){
	    
               steps{
		 echo 'cloning'
                  git 'https://github.com/alok165/DevOpsCodeDemo.git'
              }
          }
          stage('Compile'){
             agent {label 'linux_node'}
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
          stage('Package'){
		  agent {label 'linux_node2'}
              steps{
		          echo 'packing'
                  sh 'mvn package'
              }
          }
	     
          
      }
}
