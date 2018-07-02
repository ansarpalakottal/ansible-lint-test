#!groovy​
pipeline {
    agent { node {
                    label 'dev' 
                    customWorkspace '/tmp/customWorkspace' 
    }
    }
        stages {
            stage ('Ansible Code checkout ') {
                steps {
                    echo "Hello checkout" 
                      }
                }
                        stage ('package stage') {
                steps {
                  sh  '''
                        mkdir -p /tmp/output                 
                      '''
                  writeFile file: "output/usefulfile.txt", text: "This file is useful, need to archive it."
                  writeFile file: "output/uselessfile.md", text: "This file is useless, no need to archive it."
                  }
                } 
            stage ('archive stage') {
                steps {
                echo "deployed"                  
            }
          }
        }
		
	post { 
	                success {
                    archiveArtifacts artifacts: 'output/*.txt', excludes: 'output/*.md'
                    deleteDir()
            } 

	}
  }
