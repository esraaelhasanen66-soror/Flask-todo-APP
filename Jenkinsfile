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

                 
                sh "python3 -m venv venv"
                sh "source venv/bin/activate"
                sh "echo dd"
                sh "pip install --upgrade pip"
                sh "echo wel"
                sh "pwd"
                sh "whoami"
                sh "pip install -r requirements.txt"
                sh "pwd"
                sh "whoami"

                
            }
        }

        stage('Test'){

            steps{

                sh "pytest"
            }
        }


    }
}