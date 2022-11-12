pipeline {
    agent any
    
    stages {
         stage('OWASP DependencyCheck') {
      steps {
          /* --suppression suppression.xml ---- is use to remove false positive */
        dependencyCheck additionalArguments: '--format HTML --format XML --suppression suppression.xml', odcInstallation: 'Default'
      }
    }
    }
}
