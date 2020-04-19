#!groovy

pipeline {
    agent none

    options {
        buildDiscarder(logRotator(numToKeepStr: '30'))
        disableConcurrentBuilds()
        timeout(time: 6, unit: 'HOURS')
        ansiColor('xterm')
    }

stages {

stage ('Stag Deploy') {
  agent { label 'master'}
       steps{
             sh("""
               /usr/local/bin/aws s3 rm s3://www.saianjana.com/  --recursive 
               /usr/local/bin/aws s3 cp ./ s3://www.saianjana.com/  --recursive
             """)   

            }
    }           
    }

}   