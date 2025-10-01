pipeline{

    agent any
    stages{

        stage('checkout'){

            steps{

                sh "ls -al"
                sh "ls -ltr"
                sh "pwd"
                sh "whoami"
            }


        }//checkout

        stage('Install requirements'){

            steps{

                 sh '''
                    #!/bin/bash
                    set -e
                    python3 -m venv venv
                    source venv/bin/activate
                    pip install --upgrade pip
                    pip install -r requirements.txt
                '''
            }
        }

        stage('Test'){

            steps{

                sh "pytest"
            }
        }


    }
}