# gofundme
```groovy
pipeline {
   agent {
       docker {
           image 'golang'
       }
   }

   stages {
      stage('Go') {
         steps {
            sh 'go version'
         }
      }
   }
}
```
