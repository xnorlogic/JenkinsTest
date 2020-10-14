/*---------------------------------------------------------------------*/
/*Jenkinsfile                                                          */
/*Change Log :                                                         */
/*             Author       Date       Comment                         */
/*             Andy R       12/06/2018 Initial Templete                */
/*---------------------------------------------------------------------*/
pipeline {
    agent {
        node {
			/*This node is Linux*/
            label 'Zorin_Node'
        }
    }
	environment {
		APP_NAME = 'Test_GCC'
		BINARY_PATH = 'application/bin/'
	}
    stages {
		stage('Show the Root Directory') {
            steps {
                sh 'ls'
            }
		}
		stage('Make the application') {
            steps {
				/*Make the application for Linux*/
				sh '''
				cd application
				make Linux
				'''
            }
		}
		stage('Run the binary') {
            steps {
				sh './${BINARY_PATH}${APP_NAME}.deb'
				/*Clean the application*/
				sh '''
				cd application
				make clean
				'''
            }
		}
    }
	post {
		always {
            sh 'echo One way or another, I have finished'
        }
        success {
            sh 'echo I succeeeded!'	
			deleteDir()
        }
        unstable {
            sh 'echo I am unstable :/'
        }
        failure {
            sh 'echo I failed :('
        }
        changed {
            sh 'echo Things were different before...'
        }
	}
}
