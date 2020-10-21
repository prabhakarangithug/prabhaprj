#!/usr/bin/env groovy
import java.net.URL
node
    {
        stage('Git checkout'){
            git 'https://github.com/prabhakarangithug/DevOpsClassCodes.git'
        }
        stage('compile'){
            withMaven(Maven:'Mymaven'){
                sh 'mvn compile'
            }
        } 
        stage('Test'){
            try{
                withMaven(maven:'MyMaven'){
                    sh 'mvn test'
                } 
              }finally {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        stage('package'){
            withMaven (maven:'MyMaven'){
                sh 'mvn package'
            }
        }
    }
