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
                  echo "second stage"
                  }
                }
            stage ('archive stage') {
                steps {
                echo "deployed"                  
            }
          }
        }
  }
