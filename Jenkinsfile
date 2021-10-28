pipeline {
  agent any
  stages {
    stage('Create File') {
      parallel {
        stage('Change directory') {
          steps {
            dir(path: '/home/mohamed/C')
          }
        }

        stage('Create file') {
          steps {
            sh 'touch main.c'
          }
        }

        stage('Write C code') {
          steps {
            sh '''printf "
#include<stdio.h>\\n
#include <stdlib.h>\\n

int main()\\n
{\\n
 printf(\\"salut le monde\\");\\n
}\\n
"'''
          }
        }

      }
    }

    stage('Compile') {
      steps {
        sh 'gcc main.c -o main.exe'
      }
    }

    stage('execute') {
      steps {
        sh './main.exe'
      }
    }

  }
}