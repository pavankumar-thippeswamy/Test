pipeline {
	agent any

  stages {
  parallel {
  stage('build1 and build2')
		stage ('build1') {
			steps {
				sh '''  pwd
					if [[ -d './Test' ]]; then 
						cd './Test' && git pull 
					else 
						git clone https://github.com/pavankumar-thippeswamy/Test.git && cd ./Test
					fi
					mvn clean install'''
			      }
		       }
	       }
         }
         
  	stages {
		stage ('build2') {
			steps {
				sh '''  pwd
					if [[ -d './webapp' ]]; then 
						cd './webapp' && git pull 
					else 
						git clone https://github.com/pavankumar-thippeswamy/webapp.git && cd ./webapp
					fi
					mvn clean install'''
			      }
		       }
	       }
		}
