pipeline {
  agent any
  stages {
    stage('Change directory') {
      steps {
        dir(path: '/home/mohamed/C') {
          sh 'touch main.c'
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