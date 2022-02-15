//Declarative Pipeline

pipeline {
    agent any
    
    stages {
        stage('Build') {
	        steps {
	            sh 'python3 -m py_compile sources/teste_jenkin.py'
		        stash(name: 'compiled-results', includes: 'sources/*.py*')
	        }
	    }

        stage('Test') {
            steps {
                echo 'Teste echo'
            }
        }
        
        stage('Deliver'){
            steps {
		sh 'pyinstaller --onefile sources/teste_jenkin.py'
            }
            post {
                success{
                    archiveArtifacts 'dist/teste_jenkin'
               }
            }
        }
    }
}
