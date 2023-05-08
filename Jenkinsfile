
pipeline{
    tools{
       
        maven 'mymaven'
    }
	// agent any
    agent none

      stages{
         stage('Checkout'){
            agent {label 'linux_node'}
               steps{
		          echo 'cloning'
                  git 'https://github.com/alok165/DevOpsCodeDemo.git'
              }
          }

          stage('Package'){
		      agent {label 'linux_node'}
               steps{
		          echo 'packing'
                  sh 'mvn package'
              }
          }
	         
      }
}
