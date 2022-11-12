pipeline {
	agent {
		docker {
			image 'composer:latest'
		}
	}
	stages {
		stage('Build') {
			steps {
				sh 'composer install'
			}
		}
		stage('Test') {
			steps {
                sh './vendor/bin/phpunit tests'
            }
		}
		
		stage('OWASP DependencyCheck') {
      			steps {
          		/* --suppression suppression.xml ---- is use to remove false positive */
       			 dependencyCheck additionalArguments: '--format HTML --format XML --suppression suppression.xml', odcInstallation: 'Default'
      			}
    		}
	}
}
